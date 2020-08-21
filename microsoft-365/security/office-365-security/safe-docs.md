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
ms.openlocfilehash: cd689099fc6a6caa1e0e649c3f152f1de123bf12
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827474"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="03730-103">Documentos seguros en Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="03730-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="03730-104">Documentos seguros es una característica de la seguridad de Microsoft 365 E5 o Microsoft 365 E5 que usa la [protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para examinar documentos y archivos que se abren en la [vista protegida](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span><span class="sxs-lookup"><span data-stu-id="03730-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="03730-105">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="03730-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="03730-106">Documentos seguros ahora está disponible para los usuarios con la versión de Office 2004 (12730. x) o superior.</span><span class="sxs-lookup"><span data-stu-id="03730-106">Safe Documents is now generally available to users with Office Version 2004 (12730.x) or greater!</span></span> <span data-ttu-id="03730-107">Esta característica está desactivada de forma predeterminada y el administrador de seguridad la tendrá que habilitar.</span><span class="sxs-lookup"><span data-stu-id="03730-107">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="03730-108">Esta característica solo está disponible para los usuarios con la licencia de seguridad Microsoft *365 E5* o *Microsoft 365 E5* (no se incluye en los planes de ATP de Office 365).</span><span class="sxs-lookup"><span data-stu-id="03730-108">This feature is only available to users with the *Microsoft 365 E5* or *Microsoft 365 E5 Security* license (not included in Office 365 ATP plans).</span></span>

- <span data-ttu-id="03730-109">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="03730-109">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="03730-110">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="03730-110">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="03730-111">Debe tener permisos asignados para poder llevar a cabo los procedimientos de este tema.</span><span class="sxs-lookup"><span data-stu-id="03730-111">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="03730-112">Para habilitar y configurar documentos seguros, debe ser miembro de los grupos de funciones **Administración** de la organización o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="03730-112">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="03730-113">Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="03730-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="03730-114">¿Cómo administra Microsoft sus datos?</span><span class="sxs-lookup"><span data-stu-id="03730-114">How does Microsoft handle your data?</span></span>

<span data-ttu-id="03730-115">Para mantenerlo protegido, los documentos seguros envían archivos a la nube de [protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para su análisis.</span><span class="sxs-lookup"><span data-stu-id="03730-115">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span>

- <span data-ttu-id="03730-116">[Aquí](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) encontrará información sobre cómo la protección contra amenazas avanzada de Microsoft defender administra sus datos</span><span class="sxs-lookup"><span data-stu-id="03730-116">Details on how Microsoft Defender Advanced Threat Protection handles your data can be found [here](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span></span>
- <span data-ttu-id="03730-117">Además de las directrices anteriores, los archivos enviados por documentos seguros no se conservan en defender más allá del tiempo necesario para el análisis, que normalmente es inferior a 24 horas.</span><span class="sxs-lookup"><span data-stu-id="03730-117">In addition to the guidelines above, files sent by Safe Documents are not retained in Defender beyond the time needed for analysis, which is typically less than 24 hours</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="03730-118">Usar el centro de seguridad & cumplimiento para configurar documentos seguros</span><span class="sxs-lookup"><span data-stu-id="03730-118">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="03730-119">Abra el centro de seguridad & cumplimiento en <https://protection.office.com> .</span><span class="sxs-lookup"><span data-stu-id="03730-119">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="03730-120">Vaya a Directiva de **Administración de amenazas** \> **Policy** \> : **datos adjuntos seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="03730-120">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="03730-121">En la sección **ayuda para que los usuarios sigan siendo seguros cuando confíen en un archivo para abrirse fuera de la vista protegida en las aplicaciones de Office** , configure cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="03730-121">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="03730-122">**Activar documentos seguros para clientes de Office**</span><span class="sxs-lookup"><span data-stu-id="03730-122">**Turn on Safe Documents for Office clients**</span></span>

   - <span data-ttu-id="03730-123">**Permitir que los usuarios haga clic a través de la vista protegida incluso si documentos seguros identifica el archivo como malintencionado**: se recomienda no habilitar esta opción.</span><span class="sxs-lookup"><span data-stu-id="03730-123">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="03730-124">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="03730-124">When you're finished, click **Save**.</span></span>

![Página de datos adjuntos seguros de ATP](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a><span data-ttu-id="03730-126">Usar Exchange Online PowerShell o PowerShell independiente de EOP para configurar documentos seguros</span><span class="sxs-lookup"><span data-stu-id="03730-126">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="03730-127">Utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="03730-127">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="03730-128">El parámetro _EnableSafeDocs_ habilita o deshabilita los documentos seguros para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="03730-128">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="03730-129">El parámetro _AllowSafeDocsOpen_ permite o impide que los usuarios abandonen la vista protegida (es decir, que abra el documento) si el documento se ha identificado como malintencionado.</span><span class="sxs-lookup"><span data-stu-id="03730-129">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="03730-130">En este ejemplo se habilitan documentos seguros para toda la organización y se impide que los usuarios abran documentos que se han identificado como malintencionados desde la vista protegida.</span><span class="sxs-lookup"><span data-stu-id="03730-130">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="03730-131">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="03730-131">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="03730-132">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="03730-132">How do I know this worked?</span></span>

<span data-ttu-id="03730-133">Para comprobar que ha habilitado y configurado documentos seguros, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="03730-133">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="03730-134">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** \> **Policy** \> **datos adjuntos seguros de ATP**y compruebe que las selecciones en la sección **ayuda para que los usuarios sigan siendo seguros cuando confíen en un archivo para abrir una vista protegida externa en la sección aplicaciones de Office** .</span><span class="sxs-lookup"><span data-stu-id="03730-134">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="03730-135">Ejecute el siguiente comando en Exchange Online PowerShell y compruebe los valores de propiedad:</span><span class="sxs-lookup"><span data-stu-id="03730-135">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
