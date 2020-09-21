---
title: Documentos seguros en Office 365 ATP
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
ms.openlocfilehash: 5e91c226102d60368bf08b09ae5f0239f63599d5
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132229"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="2efee-103">Documentos seguros en Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="2efee-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="2efee-104">Documentos seguros es una característica de la seguridad de Microsoft 365 E5 o Microsoft 365 E5 que usa la [protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para examinar documentos y archivos que se abren en la [vista protegida](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span><span class="sxs-lookup"><span data-stu-id="2efee-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2efee-105">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="2efee-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2efee-106">Documentos seguros solo está disponible para los usuarios con licencias de seguridad de *microsoft 365 E5* o *Microsoft 365 E5* .</span><span class="sxs-lookup"><span data-stu-id="2efee-106">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="2efee-107">Estas licencias no se incluyen en los planes de la protección contra amenazas avanzada (ATP) de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2efee-107">These licenses are not included in Office 365 Advanced Threat Protection (ATP) plans.</span></span>

- <span data-ttu-id="2efee-108">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="2efee-108">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="2efee-109">Para ir directamente a la página **datos adjuntos seguros de ATP** , Abra <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="2efee-109">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="2efee-110">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2efee-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="2efee-111">Debe tener permisos asignados para poder llevar a cabo los procedimientos de este tema.</span><span class="sxs-lookup"><span data-stu-id="2efee-111">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="2efee-112">Para habilitar y configurar documentos seguros, debe ser miembro de los grupos de funciones **Administración** de la organización o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="2efee-112">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="2efee-113">Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="2efee-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="2efee-114">Para mantenerlo protegido, los documentos seguros envían archivos a la nube de [protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para su análisis.</span><span class="sxs-lookup"><span data-stu-id="2efee-114">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="2efee-115">Aquí encontrará información sobre cómo Microsoft defender ATP administra sus datos: [almacenamiento de datos y privacidad de Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="2efee-115">Details on how Microsoft Defender ATP handles your data can be found here: [Microsoft Defender ATP data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

- <span data-ttu-id="2efee-116">Los archivos enviados por documentos seguros no se conservan en defender más allá del tiempo necesario para el análisis (normalmente, menos de 24 horas).</span><span class="sxs-lookup"><span data-stu-id="2efee-116">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="2efee-117">Usar el centro de seguridad & cumplimiento para configurar documentos seguros</span><span class="sxs-lookup"><span data-stu-id="2efee-117">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="2efee-118">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** \> **Policy** \> **datos adjuntos seguros de ATP**y haga clic en **configuración global**.</span><span class="sxs-lookup"><span data-stu-id="2efee-118">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="2efee-119">En la **configuración global** vuela hacia fuera que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2efee-119">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="2efee-120">**Active los documentos seguros para los clientes de Office**: mueva el botón de alternancia a la derecha para activar la característica: ![ activar o desactivar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="2efee-120">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="2efee-121">**Permitir que los usuarios haga clic a través de la vista protegida incluso si documentos seguros identifica el archivo como malintencionado**: le recomendamos que deje esta opción desactivada (deje el botón de alternancia a la izquierda: ![ desactivar ](../../media/scc-toggle-off.png) ).</span><span class="sxs-lookup"><span data-stu-id="2efee-121">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="2efee-122">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2efee-122">When you're finished, click **Save**.</span></span>

   ![Configuración de documentos seguros después de seleccionar la configuración global en la página de datos adjuntos seguros de ATP.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="2efee-124">Usar Exchange Online PowerShell para configurar documentos seguros</span><span class="sxs-lookup"><span data-stu-id="2efee-124">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="2efee-125">Utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="2efee-125">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="2efee-126">El parámetro _EnableSafeDocs_ habilita o deshabilita los documentos seguros para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="2efee-126">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="2efee-127">El parámetro _AllowSafeDocsOpen_ permite o impide que los usuarios abandonen la vista protegida (es decir, que abra el documento) si el documento se ha identificado como malintencionado.</span><span class="sxs-lookup"><span data-stu-id="2efee-127">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="2efee-128">En este ejemplo se habilitan documentos seguros para toda la organización y se impide que los usuarios abran documentos que se han identificado como malintencionados desde la vista protegida.</span><span class="sxs-lookup"><span data-stu-id="2efee-128">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="2efee-129">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="2efee-129">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="2efee-130">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="2efee-130">How do I know this worked?</span></span>

<span data-ttu-id="2efee-131">Para comprobar que ha habilitado y configurado documentos seguros, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2efee-131">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="2efee-132">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** : \> **Policy** \> **datos adjuntos seguros de ATP**, haga clic en **configuración global**y compruebe los documentos de seguridad **Activar documentos seguros para clientes de Office** y **permitir que los usuarios haga clic en la vista protegida, incluso si documentos seguros identifica el archivo como configuración malintencionada** .</span><span class="sxs-lookup"><span data-stu-id="2efee-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="2efee-133">Ejecute el siguiente comando en Exchange Online PowerShell y compruebe los valores de propiedad:</span><span class="sxs-lookup"><span data-stu-id="2efee-133">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="2efee-134">Los siguientes archivos están disponibles para probar la protección de documentos seguros.</span><span class="sxs-lookup"><span data-stu-id="2efee-134">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="2efee-135">Estos documentos son similares a los del archivo de EICAR.TXT para probar soluciones antivirus y antivirus.</span><span class="sxs-lookup"><span data-stu-id="2efee-135">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="2efee-136">Los archivos no son dañinos, pero desencadenarán la protección de los documentos seguros.</span><span class="sxs-lookup"><span data-stu-id="2efee-136">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="2efee-137">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="2efee-137">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="2efee-138">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="2efee-138">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="2efee-139">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="2efee-139">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
