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
description: Obtenga información sobre documentos seguros en Microsoft 365 E5 o Microsoft 365 E5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a3f4ed3535c7e53774b9b567b50f7c06e99cef9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288590"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="bdc64-103">Documentos seguros en Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bdc64-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bdc64-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="bdc64-104">**Applies to**</span></span>
- [<span data-ttu-id="bdc64-105">Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="bdc64-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="bdc64-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bdc64-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="bdc64-107">Documentos seguros es una característica de Microsoft 365 E5 o Microsoft 365 E5 Security que usa [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para endpoint para examinar documentos y archivos que se abren en la vista [protegida.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)</span><span class="sxs-lookup"><span data-stu-id="bdc64-107">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bdc64-108">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="bdc64-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bdc64-109">Documentos seguros solo está disponible para los usuarios con licencias de Seguridad de *Microsoft 365 E5* o *Microsoft 365 E5.*</span><span class="sxs-lookup"><span data-stu-id="bdc64-109">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="bdc64-110">Estas licencias no se incluyen en los planes de Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="bdc64-110">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="bdc64-111">Documentos seguros es compatible con Aplicaciones de Microsoft 365 para empresas (anteriormente conocido como Office 365 ProPlus) versión 2004 o posterior.</span><span class="sxs-lookup"><span data-stu-id="bdc64-111">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="bdc64-112">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="bdc64-112">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="bdc64-113">Para ir directamente a la página **Datos adjuntos seguros** de ATP, abra <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="bdc64-113">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="bdc64-114">Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="bdc64-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="bdc64-115">Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="bdc64-115">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="bdc64-116">Para configurar la configuración de documentos seguros,  debe ser miembro de los grupos de roles Administración de la organización o **Administrador de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="bdc64-116">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="bdc64-117">Para obtener acceso de solo lectura a la configuración de documentos seguros, debe ser miembro de los grupos de roles Lector **global** o **Lector de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="bdc64-117">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="bdc64-118">Para más información, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="bdc64-118">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="bdc64-119">Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bdc64-119">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="bdc64-120">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="bdc64-120">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="bdc64-121">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="bdc64-121">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="bdc64-122">¿Cómo controla Microsoft los datos?</span><span class="sxs-lookup"><span data-stu-id="bdc64-122">How does Microsoft handle your data?</span></span>

<span data-ttu-id="bdc64-123">Para mantenerte protegido, Documentos seguros envía archivos a la nube [de Microsoft Defender para endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para su análisis.</span><span class="sxs-lookup"><span data-stu-id="bdc64-123">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="bdc64-124">Los detalles sobre cómo Microsoft Defender para puntos de conexión controla los datos se pueden encontrar aquí: Microsoft Defender para el almacenamiento de datos y la privacidad de los [puntos de conexión.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="bdc64-124">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="bdc64-125">Los archivos enviados por documentos seguros no se conservan en Defender más allá del tiempo necesario para el análisis (normalmente, menos de 24 horas).</span><span class="sxs-lookup"><span data-stu-id="bdc64-125">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="bdc64-126">Usar el Centro de seguridad & cumplimiento para configurar documentos seguros</span><span class="sxs-lookup"><span data-stu-id="bdc64-126">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="bdc64-127">En el Centro de & cumplimiento, vaya a Directiva de administración de amenazas Datos adjuntos seguros de  \>  \> **ATP** y, a continuación, haga clic **en Configuración global.**</span><span class="sxs-lookup"><span data-stu-id="bdc64-127">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="bdc64-128">En el **menú emergente Configuración** global que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="bdc64-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="bdc64-129">**Activar Documentos seguros para clientes de Office:** mueva el botón de alternancia a la derecha para activar la característica: ![ ](../../media/scc-toggle-on.png) Activar.</span><span class="sxs-lookup"><span data-stu-id="bdc64-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="bdc64-130">**Permitir a** los usuarios hacer clic a través de la vista protegida incluso si Documentos seguros identifica el archivo como malintencionado : Se recomienda dejar esta opción desactivada (deje el botón de alternancia a la izquierda: Desactivar ![ ](../../media/scc-toggle-off.png) ).</span><span class="sxs-lookup"><span data-stu-id="bdc64-130">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="bdc64-131">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bdc64-131">When you're finished, click **Save**.</span></span>

   ![Configuración de documentos seguros después de seleccionar la configuración global en la página Datos adjuntos seguros.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="bdc64-133">Usar Exchange Online PowerShell para configurar documentos seguros</span><span class="sxs-lookup"><span data-stu-id="bdc64-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="bdc64-134">Utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="bdc64-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="bdc64-135">El _parámetro EnableSafeDocs habilita_ o deshabilita documentos seguros para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="bdc64-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="bdc64-136">El _parámetro AllowSafeDocsOpen_ permite o impide que los usuarios abandonen la vista protegida (es decir, abrir el documento) si el documento se ha identificado como malintencionado.</span><span class="sxs-lookup"><span data-stu-id="bdc64-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="bdc64-137">En este ejemplo se habilitan documentos seguros para toda la organización y se impide que los usuarios abran documentos identificados como malintencionados desde la vista protegida.</span><span class="sxs-lookup"><span data-stu-id="bdc64-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="bdc64-138">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="bdc64-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="bdc64-139">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="bdc64-139">How do I know this worked?</span></span>

<span data-ttu-id="bdc64-140">Para comprobar que ha habilitado y configurado Documentos seguros, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bdc64-140">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="bdc64-141">En el Centro de seguridad y  cumplimiento de &, vaya a Directiva de administración de amenazas \>  \> Datos **adjuntos** seguros de **ATP,** haga clic en Configuración global y compruebe la opción Activar documentos seguros para clientes de **Office** y Permitir a los usuarios hacer clic en vista protegida incluso si Documentos seguros identifica el archivo como configuración malintencionada.</span><span class="sxs-lookup"><span data-stu-id="bdc64-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="bdc64-142">Ejecute el siguiente comando en Exchange Online PowerShell y compruebe los valores de propiedad:</span><span class="sxs-lookup"><span data-stu-id="bdc64-142">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="bdc64-143">Los siguientes archivos están disponibles para probar la protección de documentos seguros.</span><span class="sxs-lookup"><span data-stu-id="bdc64-143">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="bdc64-144">Estos documentos son similares al archivo EICAR.TXT para probar soluciones antimalware y antivirus.</span><span class="sxs-lookup"><span data-stu-id="bdc64-144">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="bdc64-145">Los archivos no son perjudiciales, pero activarán la protección de documentos seguros.</span><span class="sxs-lookup"><span data-stu-id="bdc64-145">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="bdc64-146">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="bdc64-146">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="bdc64-147">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="bdc64-147">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="bdc64-148">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="bdc64-148">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
