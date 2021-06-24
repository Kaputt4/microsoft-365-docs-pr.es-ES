---
title: Documentos seguros en Microsoft Defender para Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Obtenga información sobre Caja fuerte documentos en Microsoft 365 E5 o Seguridad de Microsoft 365 E5.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e1bd2150a04e51e0d06c6cd1c17a71a032df1a5
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108612"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="251d2-103">Documentos seguros en Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="251d2-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="251d2-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="251d2-104">**Applies to**</span></span>
- [<span data-ttu-id="251d2-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="251d2-105">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="251d2-106">Caja fuerte Documents es una característica de Microsoft 365 E5 o Seguridad de Microsoft 365 E5 que usa [Microsoft Defender para](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) endpoint para examinar documentos y archivos que se abren en [vista](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) protegida o Protección de aplicaciones para [Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).</span><span class="sxs-lookup"><span data-stu-id="251d2-106">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) or [Application Guard for Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="251d2-107">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="251d2-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="251d2-108">Caja fuerte Los documentos solo están disponibles para los usuarios *con Microsoft 365 E5* o *Seguridad de Microsoft 365 E5* licencias.</span><span class="sxs-lookup"><span data-stu-id="251d2-108">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="251d2-109">Estas licencias no se incluyen en Microsoft Defender para Office 365 planes.</span><span class="sxs-lookup"><span data-stu-id="251d2-109">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="251d2-110">Caja fuerte Los documentos se admiten Aplicaciones Microsoft 365 para empresas versión 2004 o posterior Office 365 ProPlus (anteriormente conocido como Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="251d2-110">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="251d2-111">Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="251d2-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="251d2-112">Para ir directamente a la **página Caja fuerte datos adjuntos,** use <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="251d2-112">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="251d2-113">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="251d2-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="251d2-114">Necesita permisos en Exchange Online **para** poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="251d2-114">You need permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="251d2-115">Para configurar Caja fuerte documentos, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="251d2-115">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="251d2-116">Para obtener acceso de solo lectura a Caja fuerte documentos, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="251d2-116">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="251d2-117">Para obtener más información, vea los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="251d2-117">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="251d2-118">Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 la cual proporciona a los usuarios los permisos necesarios _y_ para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="251d2-118">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="251d2-119">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="251d2-119">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="251d2-120">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="251d2-120">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="251d2-121">¿Cómo administra Microsoft los datos?</span><span class="sxs-lookup"><span data-stu-id="251d2-121">How does Microsoft handle your data?</span></span>

<span data-ttu-id="251d2-122">Para mantenerte protegido, Caja fuerte documentos envía archivos a la nube de [Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para su análisis.</span><span class="sxs-lookup"><span data-stu-id="251d2-122">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="251d2-123">Los detalles sobre cómo Administra Microsoft Defender para Endpoint sus datos se pueden encontrar aquí: Microsoft Defender para el almacenamiento de datos de punto [de conexión y privacidad.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="251d2-123">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="251d2-124">Los archivos enviados por Caja fuerte documentos no se conservan en Defender más allá del tiempo necesario para el análisis (normalmente, menos de 24 horas).</span><span class="sxs-lookup"><span data-stu-id="251d2-124">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-microsoft-365-defender-to-configure-safe-documents"></a><span data-ttu-id="251d2-125">Use el Microsoft 365 Defender para configurar Caja fuerte documentos</span><span class="sxs-lookup"><span data-stu-id="251d2-125">Use the Microsoft 365 Defender to configure Safe Documents</span></span>

1. <span data-ttu-id="251d2-126">Abra el portal de Microsoft 365 Defender y vaya a Correo electrónico **&** directivas de colaboración & de directivas de amenazas de reglas sección Directivas \>  \>  Caja fuerte \>  \> **datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="251d2-126">Open the Microsoft 365 Defender portal and go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="251d2-127">En la **página Caja fuerte datos adjuntos,** haga clic en **Configuración global**.</span><span class="sxs-lookup"><span data-stu-id="251d2-127">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="251d2-128">En el **menú desplegable Configuración global** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="251d2-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>
   - <span data-ttu-id="251d2-129">**Activar documentos Caja fuerte para clientes Office**: Mueva el botón de alternancia a la derecha para activar la característica: Activar ![ ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="251d2-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="251d2-130">**Permitir que** los usuarios haga clic en la vista protegida incluso si Caja fuerte Documentos identifica el archivo como malintencionado : Se recomienda dejar esta opción desactivada (dejar el botón de alternancia a la izquierda: ![ Desactivar ](../../media/scc-toggle-off.png) ).</span><span class="sxs-lookup"><span data-stu-id="251d2-130">**Allow people to click through Protected View even if Safe Documents identified the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="251d2-131">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="251d2-131">When you're finished, click **Save**.</span></span>

   ![Caja fuerte Configuración de documentos después de seleccionar Configuración global en la Caja fuerte datos adjuntos.](../../media/safe-docs-global-settings.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="251d2-133">Usar Exchange Online PowerShell para configurar Caja fuerte documentos</span><span class="sxs-lookup"><span data-stu-id="251d2-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="251d2-134">Utilice la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="251d2-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="251d2-135">El _parámetro EnableSafeDocs habilita_ o deshabilita Caja fuerte documentos para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="251d2-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="251d2-136">El _parámetro AllowSafeDocsOpen_ permite o impide que los usuarios abandonen la vista protegida (es decir, abrir el documento) si el documento se ha identificado como malintencionado.</span><span class="sxs-lookup"><span data-stu-id="251d2-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="251d2-137">En este ejemplo se Caja fuerte documentos para toda la organización e impide que los usuarios abran documentos que se hayan identificado como malintencionados desde la vista protegida.</span><span class="sxs-lookup"><span data-stu-id="251d2-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="251d2-138">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="251d2-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a><span data-ttu-id="251d2-139">Incorporación al Servicio de extremo de Microsoft Defender para habilitar las capacidades de auditoría</span><span class="sxs-lookup"><span data-stu-id="251d2-139">Onboard to the Microsoft Defender for Endpoint Service to enable auditing capabilities</span></span>

<span data-ttu-id="251d2-140">Para implementar Microsoft Defender para endpoint, debe pasar por las distintas fases de implementación.</span><span class="sxs-lookup"><span data-stu-id="251d2-140">To deploy Microsoft Defender for Endpoint, you need to go through the various phases of deployment.</span></span> <span data-ttu-id="251d2-141">Después de la incorporación, puede configurar las capacidades de auditoría en el portal de Microsoft 365 Defender auditoría.</span><span class="sxs-lookup"><span data-stu-id="251d2-141">After onboarding, you can configure auditing capabilities in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="251d2-142">Para obtener más información, [vea Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding).</span><span class="sxs-lookup"><span data-stu-id="251d2-142">To learn more, see [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding).</span></span> <span data-ttu-id="251d2-143">Si necesita ayuda adicional, consulte [Troubleshoot Microsoft Defender for Endpoint onboarding issues](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).</span><span class="sxs-lookup"><span data-stu-id="251d2-143">If you need additional help, refer to [Troubleshoot Microsoft Defender for Endpoint onboarding issues](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="251d2-144">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="251d2-144">How do I know this worked?</span></span>

<span data-ttu-id="251d2-145">Para comprobar que ha habilitado y configurado documentos Caja fuerte documentos, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="251d2-145">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="251d2-146">En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** Directivas de colaboración & Reglas Directivas de amenazas sección Directivas Caja fuerte Datos adjuntos Configuración global y compruebe la opción Activar documentos de Caja fuerte para clientes de Office y Permitir que los usuarios haga clic en la vista protegida incluso si Caja fuerte Documents identifica el archivo como una configuración malintencionada. \>  \>  \>  \>  \>   </span><span class="sxs-lookup"><span data-stu-id="251d2-146">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments** \> **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="251d2-147">Ejecute el siguiente comando en Exchange Online PowerShell y compruebe los valores de la propiedad:</span><span class="sxs-lookup"><span data-stu-id="251d2-147">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="251d2-148">Los siguientes archivos están disponibles para probar la protección Caja fuerte documentos.</span><span class="sxs-lookup"><span data-stu-id="251d2-148">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="251d2-149">Estos documentos son similares al archivo EICAR.TXT para probar soluciones antimalware y antivirus.</span><span class="sxs-lookup"><span data-stu-id="251d2-149">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="251d2-150">Los archivos no son dañinos, pero desencadenarán la protección Caja fuerte documentos.</span><span class="sxs-lookup"><span data-stu-id="251d2-150">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="251d2-151">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="251d2-151">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="251d2-152">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="251d2-152">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="251d2-153">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="251d2-153">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
