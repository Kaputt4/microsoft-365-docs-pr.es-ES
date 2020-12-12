---
title: Documentos seguros en Microsoft Defender para Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Obtenga información sobre documentos seguros en Microsoft 365 E5 o Microsoft 365 E5 Security.
ms.openlocfilehash: 0acb5d4ee0c80deebc4d0b040b046d63037037a7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659878"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="295b0-103">Documentos seguros en Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="295b0-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="295b0-104">Documentos seguros es una característica de la seguridad de Microsoft 365 E5 o Microsoft 365 E5 que usa [Microsoft defender para el punto de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para examinar documentos y archivos que se abren en la [vista protegida](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span><span class="sxs-lookup"><span data-stu-id="295b0-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="295b0-105">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="295b0-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="295b0-106">Documentos seguros solo está disponible para los usuarios con licencias de seguridad de *microsoft 365 E5* o *Microsoft 365 E5* .</span><span class="sxs-lookup"><span data-stu-id="295b0-106">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="295b0-107">Estas licencias no se incluyen en los planes de Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="295b0-107">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="295b0-108">Documentos seguros es compatible con las aplicaciones de Microsoft 365 para empresas (anteriormente conocidas como Office 365 ProPlus) versión 2004 o posterior.</span><span class="sxs-lookup"><span data-stu-id="295b0-108">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="295b0-109">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="295b0-109">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="295b0-110">Para ir directamente a la página **datos adjuntos seguros de ATP** , Abra <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="295b0-110">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="295b0-111">Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="295b0-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="295b0-112">Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento de Office 365 antes de que pueda usar este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="295b0-112">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="295b0-113">Para establecer la configuración de los documentos seguros, debe ser miembro de los grupos de funciones administración de la **organización** o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="295b0-113">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="295b0-114">Para tener acceso de solo lectura a la configuración de documentos seguros, debe ser miembro de los grupos de roles **lector global** o **lector de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="295b0-114">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="295b0-115">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="295b0-115">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="295b0-116">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="295b0-116">**Notes**:</span></span>

  - <span data-ttu-id="295b0-117">Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="295b0-117">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="295b0-118">Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="295b0-118">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="295b0-119">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="295b0-119">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="295b0-120">¿Cómo administra Microsoft sus datos?</span><span class="sxs-lookup"><span data-stu-id="295b0-120">How does Microsoft handle your data?</span></span>

<span data-ttu-id="295b0-121">Para mantenerlo protegido, los documentos seguros envían archivos a [Microsoft defender para](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) la nube de punto de conexión para su análisis.</span><span class="sxs-lookup"><span data-stu-id="295b0-121">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="295b0-122">Aquí encontrará información detallada sobre cómo se pueden encontrar Microsoft defender for Endpoint en los datos: [Microsoft defender for Endpoint Data Storage and Privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="295b0-122">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="295b0-123">Los archivos enviados por documentos seguros no se conservan en defender más allá del tiempo necesario para el análisis (normalmente, menos de 24 horas).</span><span class="sxs-lookup"><span data-stu-id="295b0-123">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="295b0-124">Usar el centro de seguridad & cumplimiento para configurar documentos seguros</span><span class="sxs-lookup"><span data-stu-id="295b0-124">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="295b0-125">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** \>  \> **datos adjuntos seguros de ATP** y haga clic en **configuración global**.</span><span class="sxs-lookup"><span data-stu-id="295b0-125">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="295b0-126">En la **configuración global** vuela hacia fuera que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="295b0-126">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="295b0-127">**Active los documentos seguros para los clientes de Office**: mueva el botón de alternancia a la derecha para activar la característica: ![ activar o desactivar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="295b0-127">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="295b0-128">**Permitir que los usuarios haga clic a través de la vista protegida incluso si documentos seguros identifica el archivo como malintencionado**: le recomendamos que deje esta opción desactivada (deje el botón de alternancia a la izquierda: ![ desactivar ](../../media/scc-toggle-off.png) ).</span><span class="sxs-lookup"><span data-stu-id="295b0-128">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="295b0-129">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="295b0-129">When you're finished, click **Save**.</span></span>

   ![Configuración de documentos seguros tras seleccionar la configuración global en la página datos adjuntos seguros.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="295b0-131">Usar Exchange Online PowerShell para configurar documentos seguros</span><span class="sxs-lookup"><span data-stu-id="295b0-131">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="295b0-132">Utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="295b0-132">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="295b0-133">El parámetro _EnableSafeDocs_ habilita o deshabilita los documentos seguros para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="295b0-133">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="295b0-134">El parámetro _AllowSafeDocsOpen_ permite o impide que los usuarios abandonen la vista protegida (es decir, que abra el documento) si el documento se ha identificado como malintencionado.</span><span class="sxs-lookup"><span data-stu-id="295b0-134">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="295b0-135">En este ejemplo se habilitan documentos seguros para toda la organización y se impide que los usuarios abran documentos que se han identificado como malintencionados desde la vista protegida.</span><span class="sxs-lookup"><span data-stu-id="295b0-135">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="295b0-136">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="295b0-136">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="295b0-137">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="295b0-137">How do I know this worked?</span></span>

<span data-ttu-id="295b0-138">Para comprobar que ha habilitado y configurado documentos seguros, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="295b0-138">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="295b0-139">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** : \>  \> **datos adjuntos seguros de ATP**, haga clic en **configuración global** y compruebe los documentos de seguridad **Activar documentos seguros para clientes de Office** y **permitir que los usuarios haga clic en la vista protegida, incluso si documentos seguros identifica el archivo como configuración malintencionada** .</span><span class="sxs-lookup"><span data-stu-id="295b0-139">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="295b0-140">Ejecute el siguiente comando en Exchange Online PowerShell y compruebe los valores de propiedad:</span><span class="sxs-lookup"><span data-stu-id="295b0-140">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="295b0-141">Los siguientes archivos están disponibles para probar la protección de documentos seguros.</span><span class="sxs-lookup"><span data-stu-id="295b0-141">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="295b0-142">Estos documentos son similares a los del archivo de EICAR.TXT para probar soluciones antivirus y antivirus.</span><span class="sxs-lookup"><span data-stu-id="295b0-142">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="295b0-143">Los archivos no son dañinos, pero desencadenarán la protección de los documentos seguros.</span><span class="sxs-lookup"><span data-stu-id="295b0-143">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="295b0-144">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="295b0-144">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="295b0-145">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="295b0-145">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="295b0-146">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="295b0-146">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
