---
title: Activar Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams
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
description: Los administradores pueden aprender a activar los datos adjuntos de Caja fuerte para SharePoint, OneDrive y Microsoft Teams, incluido cómo establecer alertas para los archivos detectados.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b64b3cfb29b3be999c9e26804e35dc4d02e48fbb
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083097"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="bbd4d-103">Activar Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbd4d-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bbd4d-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="bbd4d-104">**Applies to**</span></span>
- [<span data-ttu-id="bbd4d-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="bbd4d-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="bbd4d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbd4d-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="bbd4d-107">Microsoft Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams protege a su organización de compartir accidentalmente archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="bbd4d-108">Para obtener más información, [vea Caja fuerte attachments for SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="bbd4d-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="bbd4d-109">Este artículo contiene los pasos para habilitar y configurar Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bbd4d-110">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="bbd4d-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bbd4d-111">Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="bbd4d-112">Para ir directamente a la **página Caja fuerte datos adjuntos,** abra <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="bbd4d-112">To go directly to the **Safe Attachments** page, open <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="bbd4d-113">Para activar Caja fuerte datos adjuntos de SharePoint, OneDrive y Microsoft Teams, debe ser miembro de los  grupos  de roles Administración de la organización o Administrador de seguridad en el portal de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="bbd4d-114">Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="bbd4d-114">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="bbd4d-115">Para usar SharePoint PowerShell en línea para evitar que los usuarios descarguen archivos [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) malintencionados, debe ser miembro de los roles administrador [global](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) o administrador SharePoint en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="bbd4d-116">Compruebe que el registro de auditoría está habilitado para su organización.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="bbd4d-117">Para obtener más información, consulte [Desactivar o activar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="bbd4d-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="bbd4d-118">Espere hasta 30 minutos para que la configuración suba a efecto.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="bbd4d-119">Paso 1: Usar el portal Microsoft 365 Defender para activar Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbd4d-119">Step 1: Use the Microsoft 365 Defender portal to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="bbd4d-120">En el portal Microsoft 365 Defender, vaya **a Directivas &** de directivas de amenazas sección Directivas de amenazas Caja fuerte Datos \>  \>  \> **adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-120">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="bbd4d-121">En la **página Caja fuerte datos adjuntos,** haga clic en **Configuración global**.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-121">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="bbd4d-122">En el **menú desplegable Configuración global** que aparece, vaya a la sección Proteger archivos de **SharePoint, OneDrive y Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="bbd4d-122">In the **Global settings** fly out that appears, go to the **Protect files in SharePoint, OneDrive, and Microsoft Teams** section.</span></span>

   <span data-ttu-id="bbd4d-123">Mueva la palanca Activar defender para Office 365 para **SharePoint, OneDrive** y Microsoft Teams a la derecha Activar para activar los datos adjuntos de Caja fuerte para SharePoint, OneDrive y ![ ](../../media/scc-toggle-on.png) Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-123">Move the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="bbd4d-124">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-124">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="bbd4d-125">Use Exchange Online PowerShell para activar Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbd4d-125">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="bbd4d-126">Si prefiere usar PowerShell para activar los datos adjuntos de Caja fuerte para SharePoint, OneDrive y Microsoft Teams, conéctese [a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bbd4d-126">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="bbd4d-127">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="bbd4d-127">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="bbd4d-128">Paso 2: (recomendado) Usar SharePoint PowerShell en línea para evitar que los usuarios descarguen archivos malintencionados</span><span class="sxs-lookup"><span data-stu-id="bbd4d-128">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="bbd4d-129">De forma predeterminada, los usuarios no pueden abrir, mover, copiar o compartir archivos malintencionados detectados por los datos adjuntos de Caja fuerte para SharePoint, OneDrive y <sup>\*</sup> Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-129">By default, users can't open, move, copy, or share<sup>\*</sup> malicious files that are detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="bbd4d-130">Sin embargo, pueden eliminar y descargar archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-130">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="bbd4d-131"><sup>\*</sup> Si los usuarios van a **Administrar acceso,** la **opción** Compartir aún está disponible.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-131"><sup>\*</sup> If users go to **Manage access**, the **Share** option is still available.</span></span>

<span data-ttu-id="bbd4d-132">Para evitar que los usuarios descarguen archivos malintencionados, conéctese [a SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) en línea y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bbd4d-132">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="bbd4d-133">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="bbd4d-133">**Notes**:</span></span>

- <span data-ttu-id="bbd4d-134">Esta configuración afecta tanto a usuarios como a administradores.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-134">This setting affects both users and admins.</span></span>
- <span data-ttu-id="bbd4d-135">Los usuarios aún pueden eliminar archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-135">People can still delete malicious files.</span></span>

<span data-ttu-id="bbd4d-136">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="bbd4d-136">For detailed syntax and parameter information, see [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="bbd4d-137">Paso 3 (recomendado) Use el portal de Microsoft 365 Defender para crear una directiva de alerta para los archivos detectados</span><span class="sxs-lookup"><span data-stu-id="bbd4d-137">Step 3 (Recommended) Use the Microsoft 365 Defender portal to create an alert policy for detected files</span></span>

<span data-ttu-id="bbd4d-138">Puede crear una directiva de alerta que le informe a usted y a otros administradores cuando Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams detecte un archivo malintencionado.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-138">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="bbd4d-139">Para obtener más información sobre las alertas, vea [Create activity alerts in the Microsoft 365 Defender portal](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="bbd4d-139">To learn more about alerts, see [Create activity alerts in the Microsoft 365 Defender portal](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="bbd4d-140">En el portal Microsoft 365 Defender, vaya **a Directivas & reglas de** alerta o abra \>  <https://security.microsoft.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="bbd4d-140">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** or open <https://security.microsoft.com/alertpolicies>.</span></span>

2. <span data-ttu-id="bbd4d-141">En la página **Directiva de alertas,** haga clic **en Nueva directiva de alerta**.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-141">On the **Alert policy** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="bbd4d-142">El **Asistente para nueva directiva de** alertas se abre en un desplegable. En la **página Nombre de la alerta,** configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="bbd4d-142">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>
   - <span data-ttu-id="bbd4d-143">**Nombre:** escriba un nombre único y descriptivo.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-143">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="bbd4d-144">Por ejemplo, Archivos malintencionados en bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-144">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="bbd4d-145">**Descripción:** escriba una descripción opcional.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-145">**Description**: Type an optional description.</span></span> <span data-ttu-id="bbd4d-146">Por ejemplo, notifica a los administradores cuándo se detectan archivos malintencionados en SharePoint Online, OneDrive o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-146">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="bbd4d-147">**Gravedad:** seleccione **Bajo,** **Medio** o **Alto** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-147">**Severity**: Select **Low**, **Medium**, or **High** from the drop down list.</span></span>
   - <span data-ttu-id="bbd4d-148">**Categoría:** seleccione **Administración de amenazas** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-148">**Category**: Select **Threat management** from the drop down list.</span></span>

   <span data-ttu-id="bbd4d-149">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="bbd4d-150">En la **página Crear configuración de alerta,** configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="bbd4d-150">On the **Create alert settings** page, configure the following settings:</span></span>
   - <span data-ttu-id="bbd4d-151">**¿En qué desea alertar?** sección \> **Actividad es** \> Seleccionar malware detectado en **el** archivo de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-151">**What do you want to alert on?** section \> **Activity is** \> Select **Detected malware in file** from the drop down list.</span></span>
   - <span data-ttu-id="bbd4d-152">**¿Cómo desea que se desencadene la alerta?** sección: Deje el valor predeterminado **Cada vez que una actividad coincida con la regla** seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-152">**How do you want the alert to be triggered?** section: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="bbd4d-153">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="bbd4d-154">En la **página Establecer los destinatarios,** configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="bbd4d-154">On the **Set your recipients** page, configure the following settings:</span></span>
   - <span data-ttu-id="bbd4d-155">Compruebe **que enviar notificaciones por correo electrónico** está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-155">Verify **Send email notifications** is selected.</span></span> <span data-ttu-id="bbd4d-156">En el **cuadro Destinatarios de correo** electrónico, seleccione uno o varios administradores globales, administradores de seguridad o lectores de seguridad que deben recibir notificaciones cuando se detecte un archivo malintencionado.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-156">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="bbd4d-157">**Límite de notificación diario:** deje el valor predeterminado **Sin límite** seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-157">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="bbd4d-158">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-158">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="bbd4d-159">En la **página Revisar la configuración,** revisa la configuración.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-159">On the **Review your settings** page, review your settings.</span></span> <span data-ttu-id="bbd4d-160">Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-160">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="bbd4d-161">También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-161">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="bbd4d-162">En la sección ¿Desea activar la directiva **inmediatamente?,** deje seleccionado el valor predeterminado **Sí, encórzcala inmediatamente.**</span><span class="sxs-lookup"><span data-stu-id="bbd4d-162">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="bbd4d-163">Cuando haya terminado, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-163">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="bbd4d-164">Usar PowerShell de & seguridad para crear una directiva de alerta para los archivos detectados</span><span class="sxs-lookup"><span data-stu-id="bbd4d-164">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="bbd4d-165">Si prefiere usar PowerShell para crear la misma directiva de alerta que se describe en la sección anterior, conéctese [a PowerShell](/powershell/exchange/connect-to-scc-powershell) del Centro de seguridad & cumplimiento y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bbd4d-165">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="bbd4d-166">**Nota:** El valor _predeterminado de gravedad_ es Low.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-166">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="bbd4d-167">Para especificar Medium o High, incluya el _parámetro Severity_ y el valor en el comando.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-167">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="bbd4d-168">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span><span class="sxs-lookup"><span data-stu-id="bbd4d-168">For detailed syntax and parameter information, see [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="bbd4d-169">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="bbd4d-169">How do you know these procedures worked?</span></span>

- <span data-ttu-id="bbd4d-170">Para comprobar que ha activado correctamente los datos adjuntos de Caja fuerte para SharePoint, OneDrive y Microsoft Teams, siga uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bbd4d-170">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="bbd4d-171">En el portal de Microsoft 365 Defender, vaya **a** Directivas & reglas Directivas de amenazas sección Directivas de amenazas Caja fuerte Datos adjuntos, seleccione Configuración global y compruebe el valor de la configuración Activar defender para Office 365 para SharePoint, OneDrive y \>  \>  \>  **Microsoft Teams.** </span><span class="sxs-lookup"><span data-stu-id="bbd4d-171">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="bbd4d-172">En Exchange Online PowerShell, ejecute el siguiente comando para comprobar la configuración de la propiedad:</span><span class="sxs-lookup"><span data-stu-id="bbd4d-172">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="bbd4d-173">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="bbd4d-173">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="bbd4d-174">Para comprobar que ha bloqueado correctamente la descarga de archivos malintencionados, abra SharePoint PowerShell en línea y ejecute el siguiente comando para comprobar el valor de la propiedad:</span><span class="sxs-lookup"><span data-stu-id="bbd4d-174">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="bbd4d-175">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="bbd4d-175">For detailed syntax and parameter information, see [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="bbd4d-176">Para comprobar que ha configurado correctamente una directiva de alerta para los archivos detectados, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bbd4d-176">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>
  - <span data-ttu-id="bbd4d-177">En el portal Microsoft 365 Defender, vaya a **Directivas & reglas** de alerta Seleccione la directiva de alerta y compruebe la \>  \> configuración.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-177">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** \> select the alert policy, and verify the settings.</span></span>
  - <span data-ttu-id="bbd4d-178">En Microsoft 365 Defender powerShell del portal, reemplace por el nombre de la directiva de alerta, ejecute el siguiente comando y \<AlertPolicyName\> compruebe los valores de la propiedad:</span><span class="sxs-lookup"><span data-stu-id="bbd4d-178">In Microsoft 365 Defender portal PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="bbd4d-179">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span><span class="sxs-lookup"><span data-stu-id="bbd4d-179">For detailed syntax and parameter information, see [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="bbd4d-180">Use el [informe de estado de](view-email-security-reports.md#threat-protection-status-report) protección contra amenazas para ver información sobre los archivos detectados en SharePoint, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-180">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="bbd4d-181">En concreto, puede usar la **vista Ver datos mediante: Vista malware \> de** contenido.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-181">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
