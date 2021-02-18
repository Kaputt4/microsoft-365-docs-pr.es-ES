---
title: Activar Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Los administradores pueden aprender a activar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams, incluido cómo establecer alertas para los archivos detectados.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9688af82d194b1818d6bd3323d39bde51db20cb2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286374"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="de749-103">Activar Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de749-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="de749-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="de749-104">**Applies to**</span></span>
- [<span data-ttu-id="de749-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="de749-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="de749-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="de749-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="de749-107">Microsoft Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams protege su organización contra el uso compartido involuntario de archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="de749-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="de749-108">Para obtener más información, vea Datos adjuntos [seguros para SharePoint, OneDrive y Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="de749-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="de749-109">Este artículo contiene los pasos para habilitar y configurar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de749-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="de749-110">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="de749-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="de749-111">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="de749-111">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="de749-112">Para ir directamente a la página **Datos adjuntos seguros** de ATP, abra <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="de749-112">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="de749-113">Para activar datos adjuntos seguros para SharePoint, OneDrive y Microsoft  Teams,  debe ser miembro de los grupos de roles Administración de la organización o Administrador de seguridad en el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="de749-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="de749-114">Para más información, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="de749-114">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="de749-115">Para usar PowerShell de SharePoint Online para evitar que los usuarios descarguen archivos malintencionados, debe ser miembro de los roles Administrador [global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) o Administrador de [SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="de749-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="de749-116">Compruebe que el registro de auditoría está habilitado para su organización.</span><span class="sxs-lookup"><span data-stu-id="de749-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="de749-117">Para obtener más información, consulte [Desactivar o activar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="de749-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="de749-118">Espere hasta 30 minutos para que la configuración suba efecto.</span><span class="sxs-lookup"><span data-stu-id="de749-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="de749-119">Paso 1: Usar el Centro de seguridad & cumplimiento para activar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de749-119">Step 1: Use the Security & Compliance Center to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="de749-120">En el Centro de & cumplimiento,  vaya a Datos adjuntos seguros de ATP de la directiva de administración de amenazas y haga clic \>  \> en **Configuración global.**</span><span class="sxs-lookup"><span data-stu-id="de749-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="de749-121">En la **configuración global** que aparece, vaya a la opción Activar Defender para **Office 365 para SharePoint, OneDrive** y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de749-121">In the **Global settings** fly out that appears, go to the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="de749-122">Mueva el botón de alternancia a la derecha para activar Datos adjuntos seguros para ![ ](../../media/scc-toggle-on.png) SharePoint, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de749-122">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="de749-123">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="de749-123">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="de749-124">Usar Exchange Online PowerShell para activar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de749-124">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="de749-125">Si prefiere usar PowerShell para activar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams, conéctese a [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="de749-125">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="de749-126">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="de749-126">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="de749-127">Paso 2: (Recomendado) Usar SharePoint Online PowerShell para evitar que los usuarios descarguen archivos malintencionados</span><span class="sxs-lookup"><span data-stu-id="de749-127">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="de749-128">De forma predeterminada, los usuarios no pueden abrir, mover, copiar ni compartir archivos malintencionados detectados por ATP.</span><span class="sxs-lookup"><span data-stu-id="de749-128">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="de749-129">Sin embargo, pueden eliminar y descargar archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="de749-129">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="de749-130">Para impedir que los usuarios descarguen archivos malintencionados, conéctese a [SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="de749-130">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="de749-131">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="de749-131">**Notes**:</span></span>

- <span data-ttu-id="de749-132">Esta configuración afecta tanto a los usuarios como a los administradores.</span><span class="sxs-lookup"><span data-stu-id="de749-132">This setting affects both users and admins.</span></span>
- <span data-ttu-id="de749-133">Los usuarios aún pueden eliminar archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="de749-133">People can still delete malicious files.</span></span>

<span data-ttu-id="de749-134">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="de749-134">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="de749-135">Paso 3 (recomendado) Usar el Centro de seguridad & cumplimiento para crear una directiva de alerta para los archivos detectados</span><span class="sxs-lookup"><span data-stu-id="de749-135">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="de749-136">Puede crear una directiva de alerta que noticione a usted y a otros administradores cuando datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams detecten un archivo malintencionado.</span><span class="sxs-lookup"><span data-stu-id="de749-136">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="de749-137">Para obtener más información acerca de las alertas, vea [Crear alertas de actividad en](../../compliance/create-activity-alerts.md)el Centro de & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="de749-137">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="de749-138">En el [Centro de & cumplimiento,](https://protection.office.com)vaya **a** Directivas \> **de alertas o** abra <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="de749-138">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="de749-139">En la página **Directivas de alerta,** haga clic **en Nueva directiva de alerta.**</span><span class="sxs-lookup"><span data-stu-id="de749-139">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="de749-140">El **Asistente para nueva directiva de** alertas se abre en un menú desplegable. En la **página Nombre de la alerta,** configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="de749-140">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="de749-141">**Nombre:** escriba un nombre único y descriptivo.</span><span class="sxs-lookup"><span data-stu-id="de749-141">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="de749-142">Por ejemplo, Archivos malintencionados en bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="de749-142">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="de749-143">**Descripción:** escriba una descripción opcional.</span><span class="sxs-lookup"><span data-stu-id="de749-143">**Description**: Type an optional description.</span></span> <span data-ttu-id="de749-144">Por ejemplo, notifica a los administradores cuándo se detectan archivos malintencionados en SharePoint Online, OneDrive o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de749-144">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="de749-145">**Gravedad:** deje el valor predeterminado **Bajo** seleccionado o seleccione **Medio** o **Alto**.</span><span class="sxs-lookup"><span data-stu-id="de749-145">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="de749-146">**Seleccione una categoría:** Seleccione **Administración de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="de749-146">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="de749-147">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="de749-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="de749-148">En la **página Crear configuración de** alerta, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="de749-148">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="de749-149">**¿Qué desea alertar?: La actividad es**: Seleccionar **malware detectado en el archivo**.</span><span class="sxs-lookup"><span data-stu-id="de749-149">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="de749-150">**¿Cómo desea que se desencadene la alerta?**: Deje el valor predeterminado cada vez que una **actividad coincida con la regla** seleccionada.</span><span class="sxs-lookup"><span data-stu-id="de749-150">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="de749-151">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="de749-151">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="de749-152">En la **página Establecer los destinatarios,** configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="de749-152">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="de749-153">**Enviar notificaciones por correo** electrónico: compruebe que esta configuración está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="de749-153">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="de749-154">En el cuadro Destinatarios **de** correo electrónico, seleccione uno o más administradores globales, administradores de seguridad o lectores de seguridad que deberán recibir una notificación cuando se detecte un archivo malintencionado.</span><span class="sxs-lookup"><span data-stu-id="de749-154">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="de749-155">**Límite de notificaciones diario:** deje el valor predeterminado **Sin límite** seleccionado.</span><span class="sxs-lookup"><span data-stu-id="de749-155">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="de749-156">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="de749-156">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="de749-157">En la **página Revisar la configuración,**  revise la configuración y haga clic en Editar en cualquiera de las secciones para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="de749-157">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="de749-158">In the **Do you want to turn the policy on right away? section,** leave the default value **Yes, turn it on right away** selected.</span><span class="sxs-lookup"><span data-stu-id="de749-158">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="de749-159">Cuando haya terminado, haga clic **en Finalizar.**</span><span class="sxs-lookup"><span data-stu-id="de749-159">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="de749-160">Usar PowerShell de seguridad & cumplimiento para crear una directiva de alerta para los archivos detectados</span><span class="sxs-lookup"><span data-stu-id="de749-160">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="de749-161">Si prefiere usar PowerShell para crear la misma directiva de alerta que se describe en la sección anterior, conéctese [a PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) del Centro de seguridad & Cumplimiento y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="de749-161">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="de749-162">**Nota:** El valor _predeterminado de Gravedad_ es Bajo.</span><span class="sxs-lookup"><span data-stu-id="de749-162">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="de749-163">Para especificar Medio o Alto, incluya el _parámetro Severity_ y el valor en el comando.</span><span class="sxs-lookup"><span data-stu-id="de749-163">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="de749-164">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span><span class="sxs-lookup"><span data-stu-id="de749-164">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="de749-165">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="de749-165">How do you know these procedures worked?</span></span>

- <span data-ttu-id="de749-166">Para comprobar que ha activado correctamente datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="de749-166">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="de749-167">En el Centro de seguridad &  [cumplimiento,](https://protection.office.com)vaya a Directiva de administración de amenazas Datos adjuntos seguros de ATP, seleccione Configuración global y compruebe el valor de la opción Activar Defender para \>  \>  **Office 365 para SharePoint, OneDrive** y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de749-167">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="de749-168">En Exchange Online PowerShell, ejecute el siguiente comando para comprobar el valor de la propiedad:</span><span class="sxs-lookup"><span data-stu-id="de749-168">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="de749-169">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="de749-169">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="de749-170">Para comprobar que ha bloqueado correctamente la descarga de archivos malintencionados, abra SharePoint Online PowerShell y ejecute el siguiente comando para comprobar el valor de la propiedad:</span><span class="sxs-lookup"><span data-stu-id="de749-170">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="de749-171">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="de749-171">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="de749-172">Para comprobar que ha configurado correctamente una directiva de alerta para los archivos detectados, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="de749-172">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="de749-173">En el Centro de & cumplimiento,  vaya a Directivas de alertas y seleccione la directiva de alerta \>  \> y compruebe la configuración.</span><span class="sxs-lookup"><span data-stu-id="de749-173">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="de749-174">En PowerShell & Centro de seguridad y cumplimiento, reemplace por el nombre de la directiva de alerta, ejecute el siguiente comando y compruebe los \<AlertPolicyName\> valores de propiedad:</span><span class="sxs-lookup"><span data-stu-id="de749-174">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="de749-175">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span><span class="sxs-lookup"><span data-stu-id="de749-175">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="de749-176">Use el [informe de estado de protección contra](view-email-security-reports.md#threat-protection-status-report) amenazas para ver información sobre los archivos detectados en SharePoint, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de749-176">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="de749-177">Específicamente, puede usar los datos **de vista mediante la vista Malware \> de** contenido.</span><span class="sxs-lookup"><span data-stu-id="de749-177">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
