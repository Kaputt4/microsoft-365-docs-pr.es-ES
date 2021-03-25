---
title: Configurar directivas de datos adjuntos seguros en Microsoft Defender para Office 365
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
description: Obtenga información sobre cómo definir directivas de datos adjuntos seguros para proteger su organización de archivos malintencionados en el correo electrónico.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e96babff19ea981b953d35929813b1e08c000e32
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207366"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="58def-103">Configurar directivas de datos adjuntos seguros en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="58def-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="58def-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="58def-104">**Applies to**</span></span>
- [<span data-ttu-id="58def-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="58def-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="58def-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="58def-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="58def-107">Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](whats-new-in-defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="58def-107">This article is intended for business customers who have [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md).</span></span> <span data-ttu-id="58def-108">Si es un usuario principal que busca información sobre el examen de datos adjuntos en Outlook, vea [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="58def-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="58def-109">Datos adjuntos seguros es una característica de [Microsoft Defender para Office 365](whats-new-in-defender-for-office-365.md) que usa un entorno virtual para comprobar los datos adjuntos de los mensajes de correo electrónico entrantes después de haber sido examinados por la protección antimalware en Exchange Online Protection [(EOP),](anti-malware-protection.md)pero antes de la entrega a los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="58def-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="58def-110">Para obtener más información, vea [Datos adjuntos seguros en Microsoft Defender para Office 365](safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="58def-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](safe-attachments.md).</span></span>

<span data-ttu-id="58def-111">No hay ninguna directiva integrada o predeterminada de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="58def-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="58def-112">Para obtener el examen de datos adjuntos seguros de los datos adjuntos de mensajes de correo electrónico, debe crear una o más directivas de datos adjuntos seguros, como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="58def-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="58def-113">Puede configurar directivas de datos adjuntos seguros en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones elegibles de Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de Exchange Online, pero con suscripciones de complemento de Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="58def-113">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="58def-114">Los elementos básicos de una directiva de datos adjuntos seguros son:</span><span class="sxs-lookup"><span data-stu-id="58def-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="58def-115">**La directiva** de datos adjuntos seguros: especifica las acciones para detecciones de malware desconocidas, si se envían mensajes con datos adjuntos de malware a una dirección de correo electrónico especificada y si se entregan mensajes si no se puede completar el examen de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="58def-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="58def-116">**La regla de datos adjuntos seguros:** especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva).</span><span class="sxs-lookup"><span data-stu-id="58def-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="58def-117">La diferencia entre estos dos elementos no es obvia cuando se administran directivas de datos adjuntos seguros en el Centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="58def-117">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="58def-118">Al crear una directiva de datos adjuntos seguros, está creando una regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="58def-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="58def-119">Al modificar una directiva de datos adjuntos seguros, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada y los filtros de destinatarios modifican la regla de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="58def-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="58def-120">Todas las demás opciones modifican la directiva de datos adjuntos seguros asociada.</span><span class="sxs-lookup"><span data-stu-id="58def-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="58def-121">Al quitar una directiva de datos adjuntos seguros, se quitan la regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asociada.</span><span class="sxs-lookup"><span data-stu-id="58def-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="58def-122">En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado.</span><span class="sxs-lookup"><span data-stu-id="58def-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="58def-123">Para obtener más información, vea la sección [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="58def-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="58def-124">En el área de configuración global de la configuración de datos adjuntos seguros, se configuran características que no dependen de las directivas de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="58def-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="58def-125">Para obtener instrucciones, vea Activar datos adjuntos seguros para [SharePoint, OneDrive y Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) y Documentos seguros [en Microsoft 365 E5](safe-docs.md).</span><span class="sxs-lookup"><span data-stu-id="58def-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="58def-126">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="58def-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="58def-127">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="58def-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="58def-128">Para ir directamente a la **página Datos adjuntos** seguros, use <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="58def-128">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="58def-129">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="58def-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="58def-130">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="58def-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="58def-131">Debe tener asignados permisos antes de poder realizar los procedimientos descritos en este artículo:</span><span class="sxs-lookup"><span data-stu-id="58def-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="58def-132">Para crear, modificar y eliminar directivas de datos adjuntos  seguros, debe ser miembro de los grupos de roles  Administración de la organización o Administrador de seguridad en el Centro de cumplimiento de seguridad & y miembro del grupo de roles Administración de la organización en Exchange Online.  </span><span class="sxs-lookup"><span data-stu-id="58def-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="58def-133">Para obtener acceso de solo lectura a las directivas  de datos  adjuntos seguros, debe ser miembro de los grupos de roles Lector global o Lector de seguridad en el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="58def-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Security & Compliance Center.</span></span>

  <span data-ttu-id="58def-134">Para obtener más información, vea [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="58def-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="58def-135">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="58def-135">**Notes**:</span></span>

  - <span data-ttu-id="58def-136">Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="58def-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="58def-137">Para más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="58def-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="58def-138">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="58def-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="58def-139">Para obtener la configuración recomendada para las directivas de datos adjuntos seguros, consulte [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="58def-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="58def-140">Permitir hasta 30 minutos para que se aplique una directiva nueva o actualizada.</span><span class="sxs-lookup"><span data-stu-id="58def-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="58def-141">Usar el Centro de seguridad & cumplimiento para crear directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="58def-141">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="58def-142">La creación de una directiva de datos adjuntos seguros personalizada en el Centro de seguridad & cumplimiento crea la regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="58def-142">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="58def-143">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración de amenazas** Datos \> **adjuntos** seguros de \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="58def-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="58def-144">En la **página Datos adjuntos** seguros, haga clic **en Crear**.</span><span class="sxs-lookup"><span data-stu-id="58def-144">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="58def-145">Se **abrirá el Asistente para nueva directiva de datos adjuntos** seguros.</span><span class="sxs-lookup"><span data-stu-id="58def-145">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="58def-146">En la **página Nombre de la directiva,** configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="58def-146">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="58def-147">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="58def-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="58def-148">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="58def-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="58def-149">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="58def-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="58def-150">En la **página Configuración** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="58def-150">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="58def-151">**Respuesta de malware desconocido de datos adjuntos seguros:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="58def-151">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="58def-152">**Off**: Normalmente, no recomendamos este valor.</span><span class="sxs-lookup"><span data-stu-id="58def-152">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="58def-153">**Monitor**</span><span class="sxs-lookup"><span data-stu-id="58def-153">**Monitor**</span></span>
     - <span data-ttu-id="58def-154">**Block:** este es el valor predeterminado y el valor recomendado en Directivas de seguridad predeterminadas estándar y [estrictas.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="58def-154">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="58def-155">**Replace**</span><span class="sxs-lookup"><span data-stu-id="58def-155">**Replace**</span></span>
     - <span data-ttu-id="58def-156">**Entrega dinámica (característica de vista previa)**</span><span class="sxs-lookup"><span data-stu-id="58def-156">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="58def-157">Estos valores se explican en [Configuración de directiva de datos adjuntos seguros](safe-attachments.md#safe-attachments-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="58def-157">These values are explained in [Safe Attachments policy settings](safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="58def-158">**Envíe** los datos adjuntos a la siguiente dirección de correo electrónico:  para los valores de acción **Bloquear**, **Supervisar** o **Reemplazar**, puede seleccionar Habilitar redireccionamiento para enviar mensajes que contienen datos adjuntos de malware a la dirección de correo electrónico interna o externa especificada para su análisis e investigación.</span><span class="sxs-lookup"><span data-stu-id="58def-158">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="58def-159">La recomendación para la configuración de directivas estándar y estricta es habilitar la redirección.</span><span class="sxs-lookup"><span data-stu-id="58def-159">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="58def-160">Para obtener más información, vea [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="58def-160">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="58def-161">Aplica la selección anterior si el examen de malware para datos adjuntos tiene tiempo de espera o si se produce **un error:** la acción especificada por **Datos** adjuntos seguros se toma en mensajes incluso cuando el examen de datos adjuntos seguros no se puede completar.</span><span class="sxs-lookup"><span data-stu-id="58def-161">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="58def-162">Si ha seleccionado esta opción, seleccione siempre **Redireccionamiento habilitado**.</span><span class="sxs-lookup"><span data-stu-id="58def-162">If you selected this option, always select **Enabled redirect**.</span></span> <span data-ttu-id="58def-163">De lo contrario, los mensajes podrían perderse.</span><span class="sxs-lookup"><span data-stu-id="58def-163">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="58def-164">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="58def-164">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="58def-165">En la **página Aplicada a** que aparece, identifique los destinatarios internos a los que se aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="58def-165">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="58def-166">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="58def-166">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="58def-167">Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="58def-167">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="58def-168">Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="58def-168">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="58def-169">Haga **clic en Agregar una condición**.</span><span class="sxs-lookup"><span data-stu-id="58def-169">Click **Add a condition**.</span></span> <span data-ttu-id="58def-170">En el desplegable que aparece, seleccione una condición en **Aplicada si**:</span><span class="sxs-lookup"><span data-stu-id="58def-170">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="58def-171">**El destinatario es**: especifica uno o varios buzones, usuarios de correo o contactos de correo de la organización.</span><span class="sxs-lookup"><span data-stu-id="58def-171">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="58def-172">**El destinatario es miembro de**: Especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="58def-172">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="58def-173">**El dominio del destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en su organización.</span><span class="sxs-lookup"><span data-stu-id="58def-173">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="58def-174">Después de seleccionar la condición, aparece un desplegable correspondiente con **un cuadro Cualquiera de estos.**</span><span class="sxs-lookup"><span data-stu-id="58def-174">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="58def-175">Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="58def-175">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="58def-176">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un valor.</span><span class="sxs-lookup"><span data-stu-id="58def-176">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="58def-177">Para agregar valores adicionales, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="58def-177">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="58def-178">Para quitar entradas individuales, haga clic **en Quitar** ![ icono Quitar del ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="58def-178">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="58def-179">Para quitar toda la condición, haga clic **en Quitar** icono Quitar en ![ la ](../../media/scc-remove-icon.png) condición.</span><span class="sxs-lookup"><span data-stu-id="58def-179">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="58def-180">Para agregar una condición adicional, haga clic **en Agregar una condición** y seleccione un valor restante en Aplicado **si**.</span><span class="sxs-lookup"><span data-stu-id="58def-180">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="58def-181">Para agregar excepciones, haga clic **en Agregar una condición** y seleccione una excepción en Excepto **si**.</span><span class="sxs-lookup"><span data-stu-id="58def-181">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="58def-182">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="58def-182">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="58def-183">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="58def-183">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="58def-184">En la **página Revisar la configuración** que aparece, revisa la configuración.</span><span class="sxs-lookup"><span data-stu-id="58def-184">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="58def-185">Puede hacer clic **en Editar** en cada configuración para modificarla.</span><span class="sxs-lookup"><span data-stu-id="58def-185">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="58def-186">Cuando haya terminado, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="58def-186">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="58def-187">Usar el Centro de seguridad & cumplimiento para ver directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="58def-187">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="58def-188">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración de amenazas** Datos \> **adjuntos** seguros de \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="58def-188">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="58def-189">En la **página Datos adjuntos** seguros, seleccione una directiva de la lista y haga clic en ella (no active la casilla).</span><span class="sxs-lookup"><span data-stu-id="58def-189">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="58def-190">Los detalles de la directiva aparecen en un desplegable</span><span class="sxs-lookup"><span data-stu-id="58def-190">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="58def-191">Usar el Centro de seguridad & cumplimiento para modificar directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="58def-191">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="58def-192">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración de amenazas** Datos \> **adjuntos** seguros de \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="58def-192">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="58def-193">En la **página Datos adjuntos** seguros, seleccione una directiva de la lista y haga clic en ella (no active la casilla).</span><span class="sxs-lookup"><span data-stu-id="58def-193">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="58def-194">En el desplegable de detalles de la directiva que aparece, haga clic **en Editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="58def-194">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="58def-195">La configuración disponible en el menú desplegable que aparece es idéntica a la descrita en la sección Usar el Centro de seguridad [& cumplimiento](#use-the-security--compliance-center-to-create-safe-attachments-policies) para crear directivas de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="58def-195">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="58def-196">Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la directiva, consulte las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="58def-196">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="58def-197">Habilitar o deshabilitar directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="58def-197">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="58def-198">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración de amenazas** Datos \> **adjuntos** seguros de \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="58def-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="58def-199">Observe el valor de la **columna Estado:**</span><span class="sxs-lookup"><span data-stu-id="58def-199">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="58def-200">Mover el botón de alternancia a la izquierda</span><span class="sxs-lookup"><span data-stu-id="58def-200">Move the toggle to the left</span></span> ![Desactivar directiva](../../media/scc-toggle-off.png) <span data-ttu-id="58def-202">para deshabilitar la directiva.</span><span class="sxs-lookup"><span data-stu-id="58def-202">to disable the policy.</span></span>

   - <span data-ttu-id="58def-203">Mover el botón de alternancia a la derecha</span><span class="sxs-lookup"><span data-stu-id="58def-203">Move the toggle to the right</span></span> ![Activar directiva](../../media/scc-toggle-on.png) <span data-ttu-id="58def-205">para habilitar la directiva.</span><span class="sxs-lookup"><span data-stu-id="58def-205">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="58def-206">Establecer la prioridad de las directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="58def-206">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="58def-207">De forma predeterminada, las directivas de datos adjuntos seguros tienen una prioridad que se basa en el orden en que se crearon (las directivas más recientes son de menor prioridad que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="58def-207">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="58def-208">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="58def-208">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="58def-209">Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="58def-209">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="58def-210">Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="58def-210">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="58def-211">Las directivas de datos adjuntos seguros se muestran en el orden en que se procesan (la primera directiva tiene el **valor de** prioridad 0).</span><span class="sxs-lookup"><span data-stu-id="58def-211">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="58def-212">**Nota:** En el Centro de & cumplimiento, solo puede cambiar la prioridad de la directiva de datos adjuntos seguros después de crearla.</span><span class="sxs-lookup"><span data-stu-id="58def-212">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="58def-213">En PowerShell, puede invalidar la prioridad predeterminada al crear la regla de datos adjuntos seguros (lo que puede afectar a la prioridad de las reglas existentes).</span><span class="sxs-lookup"><span data-stu-id="58def-213">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="58def-214">Para cambiar la prioridad de una directiva, suba o baje la directiva en la lista (no puede modificar directamente el número de **Prioridad** en el Centro de seguridad y cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="58def-214">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="58def-215">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración de amenazas** Datos \> **adjuntos** seguros de \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="58def-215">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="58def-216">En la **página Datos adjuntos** seguros, seleccione una directiva de la lista y haga clic en ella (no active la casilla).</span><span class="sxs-lookup"><span data-stu-id="58def-216">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="58def-217">En el menú desplegable de detalles de la directiva que aparece, haga clic en el botón de prioridad disponible.</span><span class="sxs-lookup"><span data-stu-id="58def-217">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="58def-218">La directiva De datos adjuntos seguros con **el valor de** prioridad **0** solo tiene disponible el **botón Disminuir** prioridad.</span><span class="sxs-lookup"><span data-stu-id="58def-218">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="58def-219">La directiva datos adjuntos seguros con el valor **de prioridad** más bajo (por ejemplo, **3**) solo tiene disponible **el botón Aumentar** prioridad.</span><span class="sxs-lookup"><span data-stu-id="58def-219">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="58def-220">Si tiene tres o más directivas de datos adjuntos seguros,  las directivas entre los valores de prioridad más alta y más baja tienen disponibles los botones Aumentar prioridad y **Disminuir** prioridad.</span><span class="sxs-lookup"><span data-stu-id="58def-220">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="58def-221">Haga **clic en Aumentar prioridad** o Disminuir **prioridad** para cambiar el valor **De** prioridad.</span><span class="sxs-lookup"><span data-stu-id="58def-221">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="58def-222">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="58def-222">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="58def-223">Usar el Centro de seguridad & cumplimiento para quitar directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="58def-223">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="58def-224">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración de amenazas** Datos \> **adjuntos** seguros de \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="58def-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="58def-225">En la **página Datos adjuntos** seguros, seleccione una directiva de la lista y haga clic en ella (no active la casilla).</span><span class="sxs-lookup"><span data-stu-id="58def-225">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="58def-226">En el desplegable de detalles de directiva que aparece, haga clic en **Eliminar** directiva y, a continuación, haga clic en **Sí** en el cuadro de diálogo de advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="58def-226">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="58def-227">Usar PowerShell de Exchange Online o PowerShell EOP independiente para configurar directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="58def-227">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="58def-228">Como se describió anteriormente, una directiva de datos adjuntos seguros consta de una directiva de datos adjuntos seguros y una regla de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="58def-228">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="58def-229">En PowerShell, la diferencia entre las directivas de datos adjuntos seguros y las reglas de datos adjuntos seguros es aparente.</span><span class="sxs-lookup"><span data-stu-id="58def-229">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="58def-230">Las directivas de datos adjuntos seguros se administran mediante los cmdlets **\* -SafeAttachmentPolicy** y se administran reglas de datos adjuntos seguros mediante los cmdlets **\* -SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="58def-230">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="58def-231">En PowerShell, primero se crea la directiva de datos adjuntos seguros y, a continuación, se crea la regla de datos adjuntos seguros que identifica la directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="58def-231">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="58def-232">En PowerShell, modifica la configuración de la directiva de datos adjuntos seguros y la regla de datos adjuntos seguros por separado.</span><span class="sxs-lookup"><span data-stu-id="58def-232">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="58def-233">Al quitar una directiva de datos adjuntos seguros de PowerShell, la regla de datos adjuntos seguros correspondiente no se quita automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="58def-233">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="58def-234">Usar PowerShell para crear directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="58def-234">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="58def-235">Crear una directiva de datos adjuntos seguros en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="58def-235">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="58def-236">Cree la directiva de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="58def-236">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="58def-237">Cree la regla de datos adjuntos seguros que especifique la directiva de datos adjuntos seguros a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="58def-237">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="58def-238">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="58def-238">**Notes**:</span></span>

- <span data-ttu-id="58def-239">Puede crear una nueva regla de datos adjuntos seguros y asignarle una directiva de datos adjuntos seguros existente y no asociada.</span><span class="sxs-lookup"><span data-stu-id="58def-239">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="58def-240">Una regla de datos adjuntos seguros no se puede asociar a más de una directiva de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="58def-240">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="58def-241">Puede configurar las siguientes opciones en nuevas directivas de datos adjuntos seguros en PowerShell que no estén disponibles en el Centro de seguridad & cumplimiento hasta después de crear la directiva:</span><span class="sxs-lookup"><span data-stu-id="58def-241">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="58def-242">Cree la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="58def-242">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="58def-243">Establezca la prioridad de la directiva durante la creación (_Prioridad_ ) en _\<Number\>_ el cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="58def-243">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="58def-244">Una nueva directiva de datos adjuntos seguros que cree en PowerShell no está visible en el Centro de seguridad & cumplimiento hasta que asigne la directiva a una regla de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="58def-244">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="58def-245">Paso 1: Usar PowerShell para crear una directiva de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="58def-245">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="58def-246">Para crear una directiva de datos adjuntos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="58def-246">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="58def-247">En este ejemplo se crea una directiva de datos adjuntos segura denominada Contoso All con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="58def-247">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="58def-248">Bloquear los mensajes que se encuentran que contienen malware mediante el examen de documentos seguros (no estamos usando el parámetro _Action_ y el valor predeterminado es `Block` ).</span><span class="sxs-lookup"><span data-stu-id="58def-248">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="58def-249">El redireccionamiento está habilitado y los mensajes que se encuentran que contienen malware se envían a sec-ops@contoso.com para su análisis e investigación.</span><span class="sxs-lookup"><span data-stu-id="58def-249">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="58def-250">Si el examen de datos adjuntos seguros no está disponible o encuentra errores, no entregue el mensaje (no estamos usando el parámetro _ActionOnError_ y el valor predeterminado es `$true` ).</span><span class="sxs-lookup"><span data-stu-id="58def-250">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="58def-251">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="58def-251">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="58def-252">Paso 2: Usar PowerShell para crear una regla de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="58def-252">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="58def-253">Para crear una regla de datos adjuntos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="58def-253">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="58def-254">En este ejemplo se crea una regla de datos adjuntos segura denominada Contoso All con las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="58def-254">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="58def-255">La regla está asociada con la directiva de datos adjuntos seguros denominada Contoso All.</span><span class="sxs-lookup"><span data-stu-id="58def-255">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="58def-256">La regla se aplica a todos los destinatarios del contoso.com dominio.</span><span class="sxs-lookup"><span data-stu-id="58def-256">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="58def-257">Dado que no estamos usando el parámetro _Priority,_ se usa la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="58def-257">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="58def-258">La regla está habilitada (no estamos usando el parámetro _Enabled_ y el valor predeterminado es `$true` ).</span><span class="sxs-lookup"><span data-stu-id="58def-258">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="58def-259">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="58def-259">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="58def-260">Usar PowerShell para ver directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="58def-260">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="58def-261">Para ver las directivas de datos adjuntos seguros existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="58def-261">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="58def-262">En este ejemplo se devuelve una lista resumida de todas las directivas de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="58def-262">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="58def-263">En este ejemplo se devuelve información detallada sobre la directiva de datos adjuntos seguros denominada Ejecutivos de Contoso.</span><span class="sxs-lookup"><span data-stu-id="58def-263">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="58def-264">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="58def-264">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="58def-265">Usar PowerShell para ver reglas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="58def-265">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="58def-266">Para ver las reglas de datos adjuntos seguros existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="58def-266">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="58def-267">En este ejemplo se devuelve una lista resumida de todas las reglas de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="58def-267">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="58def-268">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="58def-268">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="58def-269">En este ejemplo se devuelve información detallada sobre la regla de datos adjuntos seguros denominada Ejecutivos de Contoso.</span><span class="sxs-lookup"><span data-stu-id="58def-269">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="58def-270">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="58def-270">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="58def-271">Usar PowerShell para modificar directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="58def-271">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="58def-272">No puede cambiar el nombre de una directiva de datos adjuntos seguros en PowerShell (el cmdlet **Set-SafeAttachmentPolicy** no tiene ningún _parámetro Name)._</span><span class="sxs-lookup"><span data-stu-id="58def-272">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="58def-273">Al cambiar el nombre de una directiva de datos adjuntos seguros en el Centro de seguridad & cumplimiento, solo se cambia el nombre de la regla de datos _adjuntos seguros._</span><span class="sxs-lookup"><span data-stu-id="58def-273">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="58def-274">De lo contrario, la misma configuración está disponible al crear una directiva de datos adjuntos seguros, tal como se describe en step [1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span><span class="sxs-lookup"><span data-stu-id="58def-274">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="58def-275">Para modificar una directiva de datos adjuntos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="58def-275">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="58def-276">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="58def-276">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="58def-277">Usar PowerShell para modificar reglas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="58def-277">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="58def-278">La única configuración que no está disponible al modificar una regla de datos adjuntos seguros en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="58def-278">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="58def-279">Para habilitar o deshabilitar las reglas de datos adjuntos seguros existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="58def-279">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="58def-280">De lo contrario, la misma configuración está disponible al crear una regla tal como se describe en el paso [2: Usar PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) para crear una regla de datos adjuntos segura anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="58def-280">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="58def-281">Para modificar una regla de datos adjuntos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="58def-281">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="58def-282">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="58def-282">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="58def-283">Usar PowerShell para habilitar o deshabilitar reglas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="58def-283">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="58def-284">Habilitar o deshabilitar una regla de datos adjuntos seguros en PowerShell habilita o deshabilita toda la directiva de datos adjuntos seguros (la regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asignada).</span><span class="sxs-lookup"><span data-stu-id="58def-284">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="58def-285">Para habilitar o deshabilitar una regla de datos adjuntos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="58def-285">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="58def-286">En este ejemplo se deshabilita la regla de datos adjuntos seguros denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="58def-286">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="58def-287">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="58def-287">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="58def-288">Para obtener información detallada sobre la sintaxis y los parámetros, vea [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) y [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="58def-288">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="58def-289">Usar PowerShell para establecer la prioridad de las reglas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="58def-289">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="58def-290">El valor de prioridad máximo que se puede establecer en una regla es 0.</span><span class="sxs-lookup"><span data-stu-id="58def-290">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="58def-291">El valor mínimo que se puede establecer depende del número de reglas.</span><span class="sxs-lookup"><span data-stu-id="58def-291">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="58def-292">Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4.</span><span class="sxs-lookup"><span data-stu-id="58def-292">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="58def-293">El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas.</span><span class="sxs-lookup"><span data-stu-id="58def-293">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="58def-294">Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="58def-294">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="58def-295">Para establecer la prioridad de una regla de datos adjuntos seguros en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="58def-295">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="58def-296">Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2.</span><span class="sxs-lookup"><span data-stu-id="58def-296">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="58def-297">Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="58def-297">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="58def-298">**Nota:** Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-SafeAttachmentRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="58def-298">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="58def-299">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="58def-299">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="58def-300">Usar PowerShell para quitar directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="58def-300">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="58def-301">Cuando usa PowerShell para quitar una directiva de datos adjuntos seguros, no se quita la regla de datos adjuntos seguros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="58def-301">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="58def-302">Para quitar una directiva de datos adjuntos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="58def-302">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="58def-303">En este ejemplo se quita la directiva de datos adjuntos seguros denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="58def-303">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="58def-304">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="58def-304">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="58def-305">Usar PowerShell para quitar reglas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="58def-305">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="58def-306">Al usar PowerShell para quitar una regla de datos adjuntos seguros, no se quita la directiva de datos adjuntos seguros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="58def-306">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="58def-307">Para quitar una regla de datos adjuntos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="58def-307">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="58def-308">En este ejemplo se quita la regla de datos adjuntos seguros denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="58def-308">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="58def-309">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="58def-309">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="58def-310">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="58def-310">How do you know these procedures worked?</span></span>

<span data-ttu-id="58def-311">Para comprobar que ha creado, modificado o quitado correctamente directivas de datos adjuntos seguros, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="58def-311">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="58def-312">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración de amenazas** Datos \> **adjuntos** seguros de \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="58def-312">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="58def-313">Compruebe la lista de directivas, sus **valores de** estado y sus **valores de** prioridad.</span><span class="sxs-lookup"><span data-stu-id="58def-313">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="58def-314">Para ver más detalles, seleccione la directiva de la lista y vea los detalles en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="58def-314">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="58def-315">En PowerShell de Exchange Online o Exchange Online Protection PowerShell, reemplace por el nombre de la directiva o regla, ejecute el siguiente comando y \<Name\> compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="58def-315">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="58def-316">Para comprobar que datos adjuntos seguros está analizando mensajes, compruebe los informes de Defender para Office 365 disponibles.</span><span class="sxs-lookup"><span data-stu-id="58def-316">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="58def-317">Para obtener más información, vea [View reports for Defender for Office 365](view-reports-for-mdo.md) y Use Explorer in the Security & Compliance [Center](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="58def-317">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
