---
title: Activar Microsoft defender para Office 365-SharePoint, OneDrive & Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Obtenga información sobre cómo activar ATP para SharePoint, OneDrive y Teams, incluido cómo establecer alertas para los archivos detectados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69cb7ffcfb06d5ccda915004a512e7eefc6eb56e
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844277"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="d3695-103">Activar ATP para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3695-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d3695-104">Microsoft defender para Office 365 para SharePoint, OneDrive y Microsoft Teams protege su organización de archivos malintencionados que se comparten de forma inadvertida.</span><span class="sxs-lookup"><span data-stu-id="d3695-104">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="d3695-105">Para obtener más información, consulte [ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="d3695-105">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="d3695-106">Este artículo contiene los pasos para habilitar y configurar ATP para SharePoint, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d3695-106">This article contains the steps for enabling and configuring ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d3695-107">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="d3695-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d3695-108">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="d3695-108">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="d3695-109">Para ir directamente a la página **datos adjuntos seguros de ATP** , Abra <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="d3695-109">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="d3695-110">Para activar ATP para SharePoint, OneDrive y Microsoft Teams, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="d3695-110">To turn on ATP for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="d3695-111">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d3695-111">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="d3695-112">Para usar PowerShell de SharePoint Online para evitar que los usuarios descarguen archivos malintencionados, debe ser miembro de los roles de administrador [global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) o [Administrador de SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) en Azure ad.</span><span class="sxs-lookup"><span data-stu-id="d3695-112">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="d3695-113">Compruebe que el registro de auditoría está habilitado para su organización.</span><span class="sxs-lookup"><span data-stu-id="d3695-113">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="d3695-114">Para obtener más información, consulte [ Desactivar o activar la búsqueda de registros de auditoría ](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="d3695-114">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="d3695-115">Espere hasta 30 minutos para que la configuración surta efecto.</span><span class="sxs-lookup"><span data-stu-id="d3695-115">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="d3695-116">Paso 1: usar el centro de seguridad & cumplimiento para activar ATP para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3695-116">Step 1: Use the Security & Compliance Center to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="d3695-117">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** \> **Policy** \> **datos adjuntos seguros de ATP** y haga clic en **configuración global**.</span><span class="sxs-lookup"><span data-stu-id="d3695-117">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments** , and click **Global settings**.</span></span>

2. <span data-ttu-id="d3695-118">En la **configuración global** vuela hacia fuera que aparece, vaya a la opción **Activar ATP para SharePoint, OneDrive y Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="d3695-118">In the **Global settings** fly out that appears, go to the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="d3695-119">Desplace el botón de alternancia a la derecha para ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) Activar ATP para SharePoint, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d3695-119">Move the toggle to the right ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) to turn on ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="d3695-120">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d3695-120">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="d3695-121">Usar Exchange Online PowerShell para activar ATP para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3695-121">Use Exchange Online PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="d3695-122">Si prefiere usar PowerShell para activar ATP para SharePoint, OneDrive y Microsoft Teams, [Conéctese a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="d3695-122">If you'd rather use PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="d3695-123">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="d3695-123">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="d3695-124">Paso 2: (recomendado) usar PowerShell de SharePoint Online para evitar que los usuarios descarguen archivos malintencionados</span><span class="sxs-lookup"><span data-stu-id="d3695-124">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="d3695-125">De forma predeterminada, los usuarios no pueden abrir, mover, copiar ni compartir archivos malintencionados detectados por ATP.</span><span class="sxs-lookup"><span data-stu-id="d3695-125">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="d3695-126">Sin embargo, pueden eliminar y descargar archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="d3695-126">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="d3695-127">Para evitar que los usuarios descarguen archivos malintencionados, [Conéctese a PowerShell de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="d3695-127">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="d3695-128">**Notas** :</span><span class="sxs-lookup"><span data-stu-id="d3695-128">**Notes** :</span></span>

- <span data-ttu-id="d3695-129">Esta configuración afecta tanto a usuarios como a administradores.</span><span class="sxs-lookup"><span data-stu-id="d3695-129">This setting affects both users and admins.</span></span>
- <span data-ttu-id="d3695-130">Los usuarios pueden seguir eliminando archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="d3695-130">People can still delete malicious files.</span></span>

<span data-ttu-id="d3695-131">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="d3695-131">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="d3695-132">Paso 3 (recomendado) usar el centro de seguridad & cumplimiento para crear una directiva de alerta para los archivos detectados</span><span class="sxs-lookup"><span data-stu-id="d3695-132">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="d3695-133">Puede crear una directiva de alerta que notifique a usted y a otros administradores Cuándo ATP para SharePoint, OneDrive y Microsoft Teams detecta un archivo malintencionado.</span><span class="sxs-lookup"><span data-stu-id="d3695-133">You can create an alert policy that notifies you and other admins when ATP for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="d3695-134">Para obtener más información acerca de las alertas, consulte [crear alertas de actividad en el centro de seguridad & cumplimiento](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="d3695-134">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="d3695-135">En el [centro de seguridad & cumplimiento](https://protection.office.com), vaya a directivas de alerta de **alertas** \> **Alert policies** o abrir <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="d3695-135">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="d3695-136">En la página **directivas de alerta** , haga clic en **nueva Directiva de alerta**.</span><span class="sxs-lookup"><span data-stu-id="d3695-136">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="d3695-137">El Asistente para **nueva Directiva de alerta** se abre en un vuelo hacia fuera. En la página **asigne un nombre a la alerta** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d3695-137">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="d3695-138">**Nombre** : escriba un nombre único y descriptivo.</span><span class="sxs-lookup"><span data-stu-id="d3695-138">**Name** : Type a unique and descriptive name.</span></span> <span data-ttu-id="d3695-139">Por ejemplo, archivos malintencionados en bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="d3695-139">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="d3695-140">**Descripción** : escriba una descripción opcional.</span><span class="sxs-lookup"><span data-stu-id="d3695-140">**Description** : Type an optional description.</span></span> <span data-ttu-id="d3695-141">Por ejemplo, notifica a los administradores Cuándo se detectan archivos malintencionados en SharePoint Online, OneDrive o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d3695-141">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="d3695-142">**Gravedad** : deje el valor predeterminado **bajo** seleccionado o seleccione **medio** o **alto**.</span><span class="sxs-lookup"><span data-stu-id="d3695-142">**Severity** : Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="d3695-143">**Seleccione una categoría** : seleccionar la **Administración de amenazas**.</span><span class="sxs-lookup"><span data-stu-id="d3695-143">**Select a category** : Select **Threat management**.</span></span>

   <span data-ttu-id="d3695-144">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d3695-144">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="d3695-145">En la página **crear configuración de alertas** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d3695-145">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="d3695-146">**¿En qué desea alertar?: Activity es** : SELECT **Detected malware in file**.</span><span class="sxs-lookup"><span data-stu-id="d3695-146">**What do you want to alert on?: Activity is** : Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="d3695-147">**¿Cómo desea que se desencadene la alerta?** : deje el valor predeterminado **cada vez que una actividad coincida con la regla** seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d3695-147">**How do you want the alert to be triggered?** : Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="d3695-148">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d3695-148">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="d3695-149">En la página **establecer los destinatarios** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d3695-149">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="d3695-150">**Enviar notificaciones por correo electrónico** : Compruebe que esta configuración está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d3695-150">**Send email notifications** : Verify this setting is selected.</span></span> <span data-ttu-id="d3695-151">En el cuadro **destinatarios de correo electrónico** , seleccione uno o más administradores globales, administradores de seguridad o lectores de seguridad que deban recibir una notificación cuando se detecte un archivo malintencionado.</span><span class="sxs-lookup"><span data-stu-id="d3695-151">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="d3695-152">**Límite de notificaciones diarias** : deje el valor predeterminado **sin límite** seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d3695-152">**Daily notification limit** : Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="d3695-153">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d3695-153">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="d3695-154">En la página **Revise la configuración** , revise la configuración y haga clic en **Editar** en cualquiera de las secciones para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="d3695-154">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="d3695-155">En la sección **¿desea activar la Directiva de inmediato?** , deje el valor predeterminado **sí, actívelo** inmediatamente seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d3695-155">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="d3695-156">Cuando haya terminado, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d3695-156">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="d3695-157">Usar seguridad & PowerShell Compliance para crear una directiva de alerta para los archivos detectados</span><span class="sxs-lookup"><span data-stu-id="d3695-157">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="d3695-158">Si prefiere usar PowerShell para crear la misma directiva de alerta que se describe en la sección anterior, [Conéctese a PowerShell del centro de cumplimiento de & de seguridad](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="d3695-158">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="d3695-159">**Nota** : el valor de _gravedad_ predeterminado es bajo.</span><span class="sxs-lookup"><span data-stu-id="d3695-159">**Note** : The default _Severity_ value is Low.</span></span> <span data-ttu-id="d3695-160">Para especificar medio o alto, incluya el parámetro _Severity_ y el valor en el comando.</span><span class="sxs-lookup"><span data-stu-id="d3695-160">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="d3695-161">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span><span class="sxs-lookup"><span data-stu-id="d3695-161">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="d3695-162">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="d3695-162">How do you know these procedures worked?</span></span>

- <span data-ttu-id="d3695-163">Para comprobar si ha activado ATP para SharePoint, OneDrive y Microsoft Teams correctamente, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d3695-163">To verify that you've successfully turned on ATP for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="d3695-164">En el [centro de seguridad & cumplimiento](https://protection.office.com), vaya a la Directiva de **Administración de amenazas** : \> **Policy** \> **datos adjuntos seguros de ATP** , seleccione **configuración global** y compruebe el valor de la opción **Activar ATP para SharePoint, OneDrive y Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="d3695-164">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments** , select **Global settings** , and verify the value of the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="d3695-165">En Exchange Online PowerShell, ejecute el siguiente comando para comprobar la configuración de la propiedad:</span><span class="sxs-lookup"><span data-stu-id="d3695-165">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="d3695-166">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="d3695-166">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="d3695-167">Para comprobar que ha bloqueado correctamente que los usuarios puedan descargar archivos malintencionados, abra PowerShell de SharePoint Online y ejecute el siguiente comando para comprobar el valor de la propiedad:</span><span class="sxs-lookup"><span data-stu-id="d3695-167">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="d3695-168">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="d3695-168">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="d3695-169">Para comprobar que ha configurado correctamente una directiva de alerta para los archivos detectados, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d3695-169">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="d3695-170">En el centro de seguridad & cumplimiento, vaya a **alertas** \> **de alertas** \> y seleccione la Directiva de alerta y Compruebe la configuración.</span><span class="sxs-lookup"><span data-stu-id="d3695-170">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="d3695-171">En el PowerShell del centro de cumplimiento de & de seguridad, reemplace \<AlertPolicyName\> por el nombre de la Directiva de alerta, ejecute el siguiente comando y compruebe los valores de propiedad:</span><span class="sxs-lookup"><span data-stu-id="d3695-171">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="d3695-172">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span><span class="sxs-lookup"><span data-stu-id="d3695-172">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="d3695-173">Use el [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report) para ver información sobre los archivos detectados en SharePoint, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d3695-173">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="d3695-174">Concretamente, puede usar la vista **ver datos por: \> malware de contenido** .</span><span class="sxs-lookup"><span data-stu-id="d3695-174">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
