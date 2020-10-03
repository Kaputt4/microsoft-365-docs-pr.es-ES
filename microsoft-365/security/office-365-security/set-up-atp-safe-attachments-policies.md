---
title: Configurar las Directivas de datos adjuntos seguros en la ATP de Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo definir directivas de datos adjuntos seguros para proteger a su organización de archivos malintencionados en el correo electrónico.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6794cf72afdb94e587e06319f87a406521ad2710
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350388"
---
# <a name="set-up-safe-attachments-policies-in-office-365-atp"></a><span data-ttu-id="d3dc1-103">Configurar las Directivas de datos adjuntos seguros en la ATP de Office 365</span><span class="sxs-lookup"><span data-stu-id="d3dc1-103">Set up Safe Attachments policies in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="d3dc1-104">Este artículo está destinado a los clientes empresariales que tienen [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="d3dc1-105">Si es un usuario doméstico que busca información sobre el análisis de datos adjuntos en Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-105">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="d3dc1-106">Datos adjuntos seguros es una característica de la [protección contra amenazas avanzada (ATP) de Office 365](office-365-atp.md) que usa un entorno virtual para comprobar los datos adjuntos en los mensajes de correo electrónico entrantes después de que hayan sido examinados por [protección antimalware en Exchange Online Protection (EOP)](anti-malware-protection.md), pero antes de entregarlos a los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-106">Safe Attachments is a feature in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="d3dc1-107">Para obtener más información, consulte [datos adjuntos seguros en Office 365 ATP](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-107">For more information, see [Safe Attachments in Office 365 ATP](atp-safe-attachments.md).</span></span>

<span data-ttu-id="d3dc1-108">No hay una directiva de datos adjuntos seguros integrada o predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-108">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="d3dc1-109">Para obtener datos adjuntos seguros del análisis de datos adjuntos de mensajes de correo electrónico, debe crear una o más directivas de datos adjuntos seguros, como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-109">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="d3dc1-110">Puede configurar directivas de datos adjuntos seguros en el centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para las organizaciones de Microsoft 365 con buzones en Exchange Online; independiente de EOP para las organizaciones sin buzones de Exchange Online, pero con Office 365 las suscripciones complementarias de ATP).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-110">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Office 365 ATP add-on subscriptions).</span></span>

<span data-ttu-id="d3dc1-111">Los elementos básicos de una directiva de datos adjuntos seguros son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-111">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="d3dc1-112">**La Directiva de datos adjuntos seguros**: especifica las acciones para detecciones de malware desconocidas, si se deben enviar mensajes con datos adjuntos de malware a una dirección de correo electrónico especificada y si se deben entregar mensajes si no se puede completar el análisis de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-112">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="d3dc1-113">**La regla de datos adjuntos seguros**: especifica la prioridad y los filtros de destinatarios (a los que se aplica la Directiva).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-113">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="d3dc1-114">La diferencia entre estos dos elementos no es obvia cuando se administran directivas de datos adjuntos seguros en el centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-114">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="d3dc1-115">Al crear una directiva de datos adjuntos seguros, en realidad está creando una regla de datos adjuntos seguros y la Directiva de datos adjuntos seguros asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-115">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="d3dc1-116">Cuando modifica una directiva de datos adjuntos seguros, la configuración relacionada con el nombre, la prioridad, habilitada o deshabilitada y los filtros de destinatarios modifican la regla de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-116">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="d3dc1-117">Todas las demás opciones modifican la Directiva de datos adjuntos seguros asociada.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-117">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="d3dc1-118">Al quitar una directiva de datos adjuntos seguros, se quitan la regla de datos adjuntos seguros y la Directiva de datos adjuntos seguros asociada.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-118">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="d3dc1-119">En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="d3dc1-120">Para obtener más información, vea la sección [usar Exchange Online PowerShell o Standalone EOP PowerShell para configurar directivas de datos adjuntos seguros](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) , más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="d3dc1-121">En el área configuración global de datos adjuntos seguros, puede configurar características que no dependen de las directivas de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-121">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="d3dc1-122">Para obtener instrucciones, consulte [Activar ATP para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) y [documentos seguros en Microsoft 365 E5](safe-docs.md).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-122">For instructions see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d3dc1-123">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="d3dc1-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d3dc1-124">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d3dc1-125">Para ir directamente a la página **datos adjuntos seguros de ATP** , use <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="d3dc1-125">To go directly to the **ATP Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="d3dc1-126">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d3dc1-127">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d3dc1-128">Para ver, crear, modificar y eliminar directivas de datos adjuntos seguros, debe pertenecer a uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-128">To view, create, modify, and delete Safe Attachments policies, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="d3dc1-129">**Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-129">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="d3dc1-130">**Administración** de la organización en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-130">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="d3dc1-131">Para conocer la configuración recomendada para las directivas de datos adjuntos seguros, consulte [configuración de datos adjuntos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-131">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="d3dc1-132">Permitir que se aplique una directiva nueva o actualizada durante un máximo de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-132">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="d3dc1-133">Usar el centro de seguridad & cumplimiento para crear directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="d3dc1-133">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="d3dc1-134">La creación de una directiva de datos adjuntos seguros personalizada en el centro de seguridad & cumplimiento crea la regla de datos adjuntos seguros y la Directiva de datos adjuntos seguros asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-134">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="d3dc1-135">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **datos adjuntos seguros de ATP**de directiva de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="d3dc1-136">En la página **datos adjuntos seguros** , haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-136">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="d3dc1-137">Se abre el Asistente para **nueva Directiva de datos adjuntos seguros** .</span><span class="sxs-lookup"><span data-stu-id="d3dc1-137">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="d3dc1-138">En la página **asigne un nombre a la Directiva** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-138">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="d3dc1-139">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-139">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="d3dc1-140">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-140">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="d3dc1-141">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-141">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="d3dc1-142">En la página de **configuración** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-142">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="d3dc1-143">**Datos adjuntos seguros respuesta de malware desconocida**: Seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-143">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="d3dc1-144">**Desactivado**: normalmente, no se recomienda este valor.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-144">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="d3dc1-145">**Monitor**</span><span class="sxs-lookup"><span data-stu-id="d3dc1-145">**Monitor**</span></span>
     - <span data-ttu-id="d3dc1-146">**Block**: este es el valor predeterminado y el valor recomendado en las directivas de seguridad estándar y estrictas [preestablecidas](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-146">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="d3dc1-147">**Replace**</span><span class="sxs-lookup"><span data-stu-id="d3dc1-147">**Replace**</span></span>
     - <span data-ttu-id="d3dc1-148">**Entrega dinámica (característica de versión preliminar)**</span><span class="sxs-lookup"><span data-stu-id="d3dc1-148">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="d3dc1-149">Estos valores se explican en la configuración de la [Directiva de datos adjuntos seguros](atp-safe-attachments.md#safe-attachments-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-149">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="d3dc1-150">**Enviar los datos adjuntos a la siguiente dirección de correo electrónico**: para los valores de la acción **bloquear**, **supervisar**o **reemplazar**, puede seleccionar **Habilitar redireccionamiento** para enviar mensajes que contienen datos adjuntos de malware a la dirección de correo electrónico interna o externa especificada para el análisis y la investigación.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-150">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="d3dc1-151">La recomendación para la configuración de directivas estándar y estricta es habilitar la redirección.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-151">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="d3dc1-152">Para obtener más información, consulte [configuración de datos adjuntos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-152">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="d3dc1-153">**Aplicar la selección anterior si el análisis de malware para archivos adjuntos se agota el tiempo de espera o error**: la acción especificada por la **respuesta de malware de datos adjuntos seguros** no se realiza en los mensajes, incluso cuando no se completa el análisis de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-153">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="d3dc1-154">Seleccione siempre esta opción si selecciona **Habilitar redirección**.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-154">Always select this option if you select **Enabled redirect**.</span></span> <span data-ttu-id="d3dc1-155">De lo contrario, los mensajes podrían perderse.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-155">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="d3dc1-156">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-156">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="d3dc1-157">En la página **aplicado a** que aparece, identifique los destinatarios internos a los que se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-157">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="d3dc1-158">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-158">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="d3dc1-159">Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-159">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="d3dc1-160">Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-160">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="d3dc1-161">Haga clic en **Agregar condición**.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-161">Click **Add a condition**.</span></span> <span data-ttu-id="d3dc1-162">En la lista desplegable que aparece, seleccione una condición en **aplicado si**:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-162">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="d3dc1-163">**El destinatario es**: especifica uno o más buzones de correo, usuarios de correo o contactos de correo de su organización.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-163">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="d3dc1-164">**El destinatario es un miembro de**: especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-164">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="d3dc1-165">**El dominio del destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en su organización.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-165">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="d3dc1-166">Después de seleccionar la condición, aparece la lista desplegable correspondiente con una **de estas** casillas.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-166">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="d3dc1-167">Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-167">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="d3dc1-168">Haga clic en el cuadro y comience a escribir para filtrar la lista y seleccionar un valor.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-168">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="d3dc1-169">Para agregar más valores, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-169">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="d3dc1-170">Para quitar entradas individuales, haga **Remove** clic en ![ el icono quitar quitar del ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-170">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="d3dc1-171">Para quitar toda la condición, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación en la condición.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-171">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="d3dc1-172">Para agregar una condición adicional, haga clic en **Agregar condición** y seleccione un valor restante en **aplicado si**.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-172">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="d3dc1-173">Para agregar excepciones, haga clic en **Agregar una condición** y seleccione una excepción en **excepto si**.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-173">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="d3dc1-174">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-174">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="d3dc1-175">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-175">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="d3dc1-176">En la página **Revise la configuración** que aparece, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-176">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="d3dc1-177">Puede hacer clic en **Editar** en cada configuración para modificarla.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-177">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="d3dc1-178">Cuando haya terminado, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-178">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="d3dc1-179">Usar el centro de seguridad & cumplimiento para ver directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="d3dc1-179">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="d3dc1-180">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **datos adjuntos seguros de ATP**de directiva de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-180">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="d3dc1-181">En la página **datos adjuntos seguros** , seleccione una directiva de la lista y haga clic en ella (no active la casilla de verificación).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-181">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="d3dc1-182">Los detalles de la Directiva aparecen en un vuelo hacia fuera</span><span class="sxs-lookup"><span data-stu-id="d3dc1-182">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="d3dc1-183">Usar el centro de seguridad & cumplimiento para modificar directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="d3dc1-183">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="d3dc1-184">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **datos adjuntos seguros de ATP**de directiva de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-184">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="d3dc1-185">En la página **datos adjuntos seguros** , seleccione una directiva de la lista y haga clic en ella (no active la casilla de verificación).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-185">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="d3dc1-186">En los detalles de la Directiva hacia fuera que aparece, haga clic en **Editar Directiva**.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-186">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="d3dc1-187">La configuración disponible en la volar hacia fuera que aparece es idéntica a la que se describe en la sección [usar el centro de seguridad & cumplimiento para crear directivas de datos adjuntos seguros](#use-the-security--compliance-center-to-create-safe-attachments-policies) .</span><span class="sxs-lookup"><span data-stu-id="d3dc1-187">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="d3dc1-188">Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la Directiva, consulte las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-188">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="d3dc1-189">Habilitar o deshabilitar las directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="d3dc1-189">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="d3dc1-190">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **datos adjuntos seguros de ATP**de directiva de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-190">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="d3dc1-191">Observe el valor de la columna **Estado** :</span><span class="sxs-lookup"><span data-stu-id="d3dc1-191">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="d3dc1-192">Mover el botón de alternancia a la izquierda</span><span class="sxs-lookup"><span data-stu-id="d3dc1-192">Move the toggle to the left</span></span> ![Desactivar Directiva](../../media/scc-toggle-off.png) <span data-ttu-id="d3dc1-194">para deshabilitar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-194">to disable the policy.</span></span>

   - <span data-ttu-id="d3dc1-195">Mover el botón de alternancia a la derecha</span><span class="sxs-lookup"><span data-stu-id="d3dc1-195">Move the toggle to the right</span></span> ![Activar la Directiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) <span data-ttu-id="d3dc1-197">para habilitar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-197">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="d3dc1-198">Establecer la prioridad de las directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="d3dc1-198">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="d3dc1-199">De forma predeterminada, las directivas de datos adjuntos seguros reciben una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen prioridad más baja que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-199">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="d3dc1-200">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-200">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="d3dc1-201">Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-201">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="d3dc1-202">Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-202">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="d3dc1-203">Las directivas de datos adjuntos seguros se muestran en el orden en que se procesan (la primera Directiva tiene el valor de **prioridad** 0).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-203">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="d3dc1-204">**Nota**: en el centro de seguridad & cumplimiento, solo puede cambiar la prioridad de la Directiva de datos adjuntos seguros después de crearla.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-204">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="d3dc1-205">En PowerShell, puede invalidar la prioridad predeterminada al crear la regla de datos adjuntos seguros (lo que puede afectar a la prioridad de las reglas existentes).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-205">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="d3dc1-206">Para cambiar la prioridad de una directiva, suba o baje la directiva en la lista (no puede modificar directamente el número de **Prioridad** en el Centro de seguridad y cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-206">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="d3dc1-207">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **datos adjuntos seguros de ATP**de directiva de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-207">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="d3dc1-208">En la página **datos adjuntos seguros** , seleccione una directiva de la lista y haga clic en ella (no active la casilla de verificación).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-208">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="d3dc1-209">En los detalles de la Directiva volar hacia fuera que aparece, haga clic en el botón prioridad disponible.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-209">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="d3dc1-210">La Directiva de datos adjuntos seguros con el valor de **prioridad** **0** sólo tiene disponible el botón **disminuir prioridad** .</span><span class="sxs-lookup"><span data-stu-id="d3dc1-210">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="d3dc1-211">La Directiva de datos adjuntos seguros con el valor de **prioridad** más bajo (por ejemplo, **3**) solo tiene el botón **aumentar prioridad** disponible.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-211">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="d3dc1-212">Si tiene tres o más directivas de datos adjuntos seguros, las directivas entre los valores de prioridad mayor y menor tienen los botones **aumentar prioridad** y **disminuir prioridad** disponibles.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-212">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="d3dc1-213">Haga clic en **aumentar prioridad** o **disminuir prioridad** para cambiar el valor de **prioridad** .</span><span class="sxs-lookup"><span data-stu-id="d3dc1-213">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="d3dc1-214">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-214">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="d3dc1-215">Usar el centro de seguridad & cumplimiento para quitar directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="d3dc1-215">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="d3dc1-216">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **datos adjuntos seguros de ATP**de directiva de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-216">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="d3dc1-217">En la página **datos adjuntos seguros** , seleccione una directiva de la lista y haga clic en ella (no active la casilla de verificación).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-217">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="d3dc1-218">En los detalles de la Directiva que aparecen, haga clic en **eliminar Directiva**y, a continuación, haga clic en **sí** en el cuadro de diálogo de advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-218">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="d3dc1-219">Usar Exchange Online PowerShell o PowerShell independiente de EOP para configurar directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="d3dc1-219">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="d3dc1-220">Como se ha descrito anteriormente, una directiva de datos adjuntos seguros consta de una directiva de datos adjuntos seguros y una regla de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-220">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="d3dc1-221">En PowerShell, es evidente la diferencia entre las directivas de datos adjuntos seguros y las reglas de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-221">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="d3dc1-222">Para administrar las directivas de datos adjuntos seguros, puede usar los cmdlets \*\* \* -SafeAttachmentPolicy\*\* y administrar reglas de datos adjuntos seguras con los cmdlets \*\* \* -SafeAttachmentRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="d3dc1-222">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="d3dc1-223">En PowerShell, se crea la Directiva de datos adjuntos seguros en primer lugar y, a continuación, se crea la regla de datos adjuntos seguros que identifica la Directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-223">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="d3dc1-224">En PowerShell, la configuración de la Directiva de datos adjuntos seguros y la regla de datos adjuntos seguros se modifica por separado.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-224">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="d3dc1-225">Cuando se quita una directiva de datos adjuntos seguros de PowerShell, la regla de datos adjuntos seguros correspondiente no se quita automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-225">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="d3dc1-226">Usar PowerShell para crear directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="d3dc1-226">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="d3dc1-227">La creación de una directiva de datos adjuntos seguros en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-227">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="d3dc1-228">Cree la Directiva de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-228">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="d3dc1-229">Cree la regla de datos adjuntos seguros que especifica la Directiva de datos adjuntos seguros a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-229">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="d3dc1-230">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-230">**Notes**:</span></span>

- <span data-ttu-id="d3dc1-231">Puede crear una nueva regla de datos adjuntos seguros y asignar una directiva de datos adjuntos seguros existente no asociada.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-231">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="d3dc1-232">No se puede asociar una regla de datos adjuntos seguros con más de una directiva de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-232">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="d3dc1-233">Puede configurar las siguientes opciones en nuevas directivas de datos adjuntos seguros en PowerShell que no están disponibles en el centro de seguridad & cumplimiento hasta que se crea la Directiva:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-233">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="d3dc1-234">Cree la nueva directiva como deshabilitada (_habilitada_ `$false` en el cmdlet **New-SafeAttachmentRule** ).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-234">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="d3dc1-235">Establezca la prioridad de la Directiva durante la creación (_prioridad_ _\<Number\>_ ) en el cmdlet **New-SafeAttachmentRule** ).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-235">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="d3dc1-236">Una nueva Directiva de datos adjuntos seguros que se crea en PowerShell no es visible en el centro de seguridad & cumplimiento hasta que se asigna la Directiva a una regla de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-236">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="d3dc1-237">Paso 1: usar PowerShell para crear una directiva de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="d3dc1-237">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="d3dc1-238">Para crear una directiva de datos adjuntos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-238">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="d3dc1-239">En este ejemplo se crea una directiva de datos adjuntos seguros denominada contoso All con los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-239">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="d3dc1-240">Bloquear mensajes que se encuentren para contener malware mediante documentos seguros análisis (no estamos usando el parámetro _Action_ y el valor predeterminado es `Block` ).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-240">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="d3dc1-241">La redirección está habilitada, y los mensajes que contienen malware se envían a sec-ops@contoso.com para el análisis y la investigación.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-241">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="d3dc1-242">Si el análisis de datos adjuntos seguros no está disponible o encuentra errores, no entrega el mensaje (no se usa el parámetro _ActionOnError_ y el valor predeterminado es `$true` ).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-242">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="d3dc1-243">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-243">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="d3dc1-244">Paso 2: usar PowerShell para crear una regla de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="d3dc1-244">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="d3dc1-245">Para crear una regla de datos adjuntos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-245">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="d3dc1-246">En este ejemplo se crea una regla de datos adjuntos seguros denominada contoso All con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-246">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="d3dc1-247">La regla está asociada a la Directiva de datos adjuntos seguros llamada contoso ALL.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-247">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="d3dc1-248">La regla se aplica a todos los destinatarios del dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-248">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="d3dc1-249">Como no se usa el parámetro _Priority_ , se usa la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-249">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="d3dc1-250">La regla está habilitada (no se usa el parámetro _Enabled_ y el valor predeterminado es `$true` ).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-250">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="d3dc1-251">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-251">For detailed syntax and parameter information, see [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="d3dc1-252">Usar PowerShell para ver las directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="d3dc1-252">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="d3dc1-253">Para ver las directivas de datos adjuntos seguros existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-253">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="d3dc1-254">En este ejemplo se devuelve una lista resumida de todas las directivas de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-254">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="d3dc1-255">En este ejemplo se muestra información detallada sobre la Directiva de datos adjuntos seguros denominada ejecutivos de contoso.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-255">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="d3dc1-256">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-256">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="d3dc1-257">Usar PowerShell para ver las reglas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="d3dc1-257">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="d3dc1-258">Para ver las reglas de datos adjuntos seguros existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-258">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="d3dc1-259">En este ejemplo se devuelve una lista resumida de todas las reglas de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-259">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="d3dc1-260">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-260">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="d3dc1-261">En este ejemplo se muestra información detallada sobre la regla de datos adjuntos seguros denominada ejecutivos de contoso.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-261">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="d3dc1-262">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-262">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="d3dc1-263">Usar PowerShell para modificar directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="d3dc1-263">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="d3dc1-264">No puede cambiar el nombre de una directiva de datos adjuntos seguros en PowerShell (el cmdlet **set-SafeAttachmentPolicy** no tiene ningún parámetro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-264">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="d3dc1-265">Al cambiar el nombre de una directiva de datos adjuntos seguros en el centro de seguridad & cumplimiento, sólo cambia el nombre de la _regla_de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-265">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="d3dc1-266">De lo contrario, la misma configuración está disponible cuando se crea una directiva de datos adjuntos seguros, tal como se describe en la sección [paso 1: usar PowerShell para crear una directiva de datos adjuntos seguros](#step-1-use-powershell-to-create-a-safe-attachment-policy) , anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-266">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="d3dc1-267">Para modificar una directiva de datos adjuntos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-267">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="d3dc1-268">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-268">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="d3dc1-269">Usar PowerShell para modificar reglas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="d3dc1-269">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="d3dc1-270">La única opción que no está disponible cuando se modifica una regla de datos adjuntos seguros en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-270">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="d3dc1-271">Para habilitar o deshabilitar las reglas de datos adjuntos seguros existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-271">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="d3dc1-272">De lo contrario, la misma configuración está disponible cuando se crea una regla, tal y como se describe en la sección [paso 2: usar PowerShell para crear una regla de datos adjuntos seguros](#step-2-use-powershell-to-create-a-safe-attachment-rule) , anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-272">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="d3dc1-273">Para modificar una regla de datos adjuntos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-273">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="d3dc1-274">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-274">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="d3dc1-275">Usar PowerShell para habilitar o deshabilitar reglas de datos adjuntos seguras</span><span class="sxs-lookup"><span data-stu-id="d3dc1-275">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="d3dc1-276">Habilitar o deshabilitar una regla de datos adjuntos seguros en PowerShell habilita o deshabilita toda la Directiva de datos adjuntos seguros (la regla de datos adjuntos seguros y la Directiva de datos adjuntos seguros asignada).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-276">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="d3dc1-277">Para habilitar o deshabilitar una regla de datos adjuntos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-277">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="d3dc1-278">En este ejemplo se deshabilita la regla de datos adjuntos seguros denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-278">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="d3dc1-279">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-279">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="d3dc1-280">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) y [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-280">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="d3dc1-281">Usar PowerShell para establecer la prioridad de las reglas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="d3dc1-281">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="d3dc1-282">El valor de prioridad máximo que se puede establecer en una regla es 0.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-282">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="d3dc1-283">El valor mínimo que se puede establecer depende del número de reglas.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-283">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="d3dc1-284">Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-284">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="d3dc1-285">El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-285">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="d3dc1-286">Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-286">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="d3dc1-287">Para establecer la prioridad de una regla de datos adjuntos seguros en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-287">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="d3dc1-288">Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-288">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="d3dc1-289">Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-289">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="d3dc1-290">**Nota**: para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-SafeAttachmentRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-290">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="d3dc1-291">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-291">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="d3dc1-292">Usar PowerShell para quitar directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="d3dc1-292">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="d3dc1-293">Cuando se usa PowerShell para quitar una directiva de datos adjuntos seguros, no se quita la regla de datos adjuntos seguros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-293">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="d3dc1-294">Para quitar una directiva de datos adjuntos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-294">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="d3dc1-295">En este ejemplo se quita la Directiva de datos adjuntos seguros denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-295">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="d3dc1-296">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-296">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="d3dc1-297">Usar PowerShell para quitar reglas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="d3dc1-297">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="d3dc1-298">Cuando se usa PowerShell para quitar una regla de datos adjuntos seguros, no se quita la Directiva de datos adjuntos seguros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-298">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="d3dc1-299">Para quitar una regla de datos adjuntos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-299">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="d3dc1-300">En este ejemplo se quita la regla de datos adjuntos seguros denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-300">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="d3dc1-301">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-301">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="d3dc1-302">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="d3dc1-302">How do you know these procedures worked?</span></span>

<span data-ttu-id="d3dc1-303">Para comprobar que las directivas de datos adjuntos seguras se crearon, modificaron o quitaron correctamente, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-303">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="d3dc1-304">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **datos adjuntos seguros de ATP**de directiva de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-304">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="d3dc1-305">Compruebe la lista de directivas, sus valores de **Estado** y sus valores de **prioridad** .</span><span class="sxs-lookup"><span data-stu-id="d3dc1-305">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="d3dc1-306">Para ver más detalles, seleccione la Directiva de la lista y vea los detalles en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-306">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="d3dc1-307">En PowerShell de Exchange Online PowerShell o Exchange Online Protection, reemplace \<Name\> por el nombre de la Directiva o regla, ejecute el siguiente comando y Compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="d3dc1-307">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="d3dc1-308">Para comprobar que los datos adjuntos seguros están examinando los mensajes, consulte los informes de protección contra amenazas avanzada disponibles.</span><span class="sxs-lookup"><span data-stu-id="d3dc1-308">To verify that Safe Attachments is scanning messages, check the available Advanced Threat Protection reports.</span></span> <span data-ttu-id="d3dc1-309">Para obtener más información, consulte [View Reports for Office 365 ATP](view-reports-for-atp.md) and [use Explorer en el centro de seguridad & cumplimiento](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="d3dc1-309">For more information, see [View reports for Office 365 ATP](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
