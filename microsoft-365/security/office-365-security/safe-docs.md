---
title: Documentos seguros en Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Obtenga información sobre documentos seguros en Office 365 ATP.
ms.openlocfilehash: b9e5a42b3d6be987170049ad5f0f451f8280fbff
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209168"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a><span data-ttu-id="d9511-103">Documentos seguros en Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="d9511-103">Safe Documents in Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="d9511-104">Documentos seguros es una característica de Office 365 Advanced Threat Protection (Office 365 ATP) que usa la [protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para examinar documentos y archivos que se abren en la [vista protegida](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span><span class="sxs-lookup"><span data-stu-id="d9511-104">Safe Documents is a feature in Office 365 Advanced Threat Protection (Office 365 ATP) that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d9511-105">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="d9511-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d9511-106">Esta característica solo está disponible para los usuarios con la licencia de seguridad Microsoft 365 E5 o Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="d9511-106">This feature is only available to users with the Microsoft 365 E5 or Microsoft 365 E5 Security license.</span></span>

- <span data-ttu-id="d9511-107">Documentos seguros está actualmente disponible para la versión preliminar pública, disponible para los usuarios que forman parte del [programa de Office Insider](https://insider.office.com/en-us/join) en el canal mensual (dirigido), con office versión 2002 (12527,20092) o posterior.</span><span class="sxs-lookup"><span data-stu-id="d9511-107">Safe Documents is currently available for public preview, available to users that are part of the [Office Insider Program](https://insider.office.com/en-us/join) on the 'Monthly Channel (Targeted)' with Office Version 2002 (12527.20092) or greater.</span></span> <span data-ttu-id="d9511-108">Esta característica está desactivada de forma predeterminada y el administrador de seguridad la tendrá que habilitar.</span><span class="sxs-lookup"><span data-stu-id="d9511-108">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="d9511-109">Para conectarse a PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d9511-109">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d9511-110">Para conectarse a PowerShell de Exchange Online Protection, vea [conectarse a PowerShell de Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="d9511-110">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d9511-111">Debe tener permisos asignados para poder llevar a cabo los procedimientos de este tema.</span><span class="sxs-lookup"><span data-stu-id="d9511-111">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="d9511-112">Para habilitar y configurar documentos seguros, debe ser miembro de los grupos de funciones **Administración** de la organización o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="d9511-112">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="d9511-113">Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d9511-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="d9511-114">¿Cómo administra Microsoft sus datos?</span><span class="sxs-lookup"><span data-stu-id="d9511-114">How does Microsoft handle your data?</span></span>

<span data-ttu-id="d9511-115">Para mantenerlo protegido, los documentos seguros envían archivos a la nube de [protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para su análisis.</span><span class="sxs-lookup"><span data-stu-id="d9511-115">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span>

- <span data-ttu-id="d9511-116">[Aquí](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) encontrará información sobre cómo la protección avanzada de subprocesos de Microsoft defender administra sus datos</span><span class="sxs-lookup"><span data-stu-id="d9511-116">Details on how Microsoft Defender Advanced Thread Protection handles your data can be found [here](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span></span>
- <span data-ttu-id="d9511-117">Además de las directrices anteriores, los archivos enviados por documentos seguros no se conservan en defender más allá del tiempo necesario para el análisis, que normalmente es inferior a 24 horas.</span><span class="sxs-lookup"><span data-stu-id="d9511-117">In addition to the guidelines above, files sent by Safe Documents are not retained in Defender beyond the time needed for analysis, which is typically less than 24 hours</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="d9511-118">Usar el centro de seguridad & cumplimiento para configurar documentos seguros</span><span class="sxs-lookup"><span data-stu-id="d9511-118">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="d9511-119">Abra el centro de seguridad & cumplimiento en <https://protection.office.com> .</span><span class="sxs-lookup"><span data-stu-id="d9511-119">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="d9511-120">Vaya a Directiva de **Administración de amenazas** \> **Policy** \> : **datos adjuntos seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="d9511-120">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="d9511-121">En la sección **ayuda para que los usuarios sigan siendo seguros cuando confíen en un archivo para abrirse fuera de la vista protegida en las aplicaciones de Office** , configure cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d9511-121">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="d9511-122">**Activar documentos seguros para clientes de Office (los archivos también se enviarán a la nube de Microsoft para análisis profundos)**</span><span class="sxs-lookup"><span data-stu-id="d9511-122">**Turn on Safe Documents for Office clients (Files will also be sent to Microsoft Cloud for deep analyses)**</span></span>

   - <span data-ttu-id="d9511-123">**Permitir que los usuarios haga clic a través de la vista protegida incluso si documentos seguros identifica el archivo como malintencionado**: se recomienda no habilitar esta opción.</span><span class="sxs-lookup"><span data-stu-id="d9511-123">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="d9511-124">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d9511-124">When you're finished, click **Save**.</span></span>

![Página de datos adjuntos seguros de ATP](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-safe-documents"></a><span data-ttu-id="d9511-126">Usar Exchange Online PowerShell o Exchange Online Protection PowerShell para configurar documentos seguros</span><span class="sxs-lookup"><span data-stu-id="d9511-126">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="d9511-127">Use la sintaxis que se muestre a continuación:</span><span class="sxs-lookup"><span data-stu-id="d9511-127">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- <span data-ttu-id="d9511-128">El parámetro _EnableSafeDocs_ habilita o deshabilita los documentos seguros para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="d9511-128">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="d9511-129">El parámetro _AllowSafeDocsOpen_ permite o impide que los usuarios abandonen la vista protegida (es decir, que abra el documento) si el documento se ha identificado como malintencionado.</span><span class="sxs-lookup"><span data-stu-id="d9511-129">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="d9511-130">En este ejemplo se habilitan documentos seguros para toda la organización y se impide que los usuarios abran documentos que se han identificado como malintencionados desde la vista protegida.</span><span class="sxs-lookup"><span data-stu-id="d9511-130">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="d9511-131">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="d9511-131">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="d9511-132">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="d9511-132">How do I know this worked?</span></span>

<span data-ttu-id="d9511-133">Para comprobar que ha habilitado y configurado documentos seguros, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d9511-133">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="d9511-134">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** \> **Policy** \> **datos adjuntos seguros de ATP**y compruebe que las selecciones en la sección **ayuda para que los usuarios sigan siendo seguros cuando confíen en un archivo para abrir una vista protegida externa en la sección aplicaciones de Office** .</span><span class="sxs-lookup"><span data-stu-id="d9511-134">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="d9511-135">Ejecute el siguiente comando en Exchange Online PowerShell y compruebe los valores de propiedad:</span><span class="sxs-lookup"><span data-stu-id="d9511-135">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
