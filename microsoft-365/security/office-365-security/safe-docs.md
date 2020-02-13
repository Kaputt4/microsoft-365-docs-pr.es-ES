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
ms.openlocfilehash: db73fc152a5a580a28bf6d8424ebc2a139cf3303
ms.sourcegitcommit: c2a36b16e354e20db5fd6275175ca856eae55bfc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "41960364"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a><span data-ttu-id="34261-103">Documentos seguros en Office 365 protección contra amenazas avanzada</span><span class="sxs-lookup"><span data-stu-id="34261-103">Safe Documents in Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="34261-104">Documentos seguros es una característica de la protección contra amenazas avanzada (ATP) de Office 365 que usa la [protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para examinar documentos y archivos que se abren en la [vista protegida](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span><span class="sxs-lookup"><span data-stu-id="34261-104">Safe Documents is a feature in Office 365 Advanced Threat Protection (ATP) that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="34261-105">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="34261-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="34261-106">Para conectarse al PowerShell de Exchange Online, consulte [Conectarse al PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="34261-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="34261-107">Para conectarse a PowerShell de Exchange Online Protection, vea [conectarse a PowerShell de Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="34261-107">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="34261-108">Debe tener permisos asignados para poder llevar a cabo los procedimientos de este tema.</span><span class="sxs-lookup"><span data-stu-id="34261-108">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="34261-109">Para habilitar y configurar documentos seguros, debe ser miembro de los grupos de funciones **Administración** de la organización o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="34261-109">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="34261-110">Para obtener más información acerca de los grupos de roles en el centro de seguridad & cumplimiento, consulte [Permissions in the Office 365 security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="34261-110">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-office-365-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="34261-111">Usar el centro de cumplimiento de & de seguridad de Office 365 para configurar documentos seguros</span><span class="sxs-lookup"><span data-stu-id="34261-111">Use the Office 365 Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="34261-112">Abra el centro de cumplimiento de & de seguridad <https://protection.office.com>de Office 365 en.</span><span class="sxs-lookup"><span data-stu-id="34261-112">Open the Office 365 Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="34261-113">Vaya a \*\*\*\* \> **Directiva** \> de administración de amenazas: **datos adjuntos seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="34261-113">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="34261-114">En la sección **ayuda para que los usuarios sigan siendo seguros cuando confíen en un archivo para abrirse fuera de la vista protegida en las aplicaciones de Office** , configure cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="34261-114">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="34261-115">**Activar documentos seguros para clientes de Office (los archivos también se enviarán a la nube de Microsoft para análisis profundos)**</span><span class="sxs-lookup"><span data-stu-id="34261-115">**Turn on Safe Documents for Office clients (Files will also be sent to Microsoft Cloud for deep analyses)**</span></span>

   - <span data-ttu-id="34261-116">**Permitir que los usuarios haga clic a través de la vista protegida incluso si documentos seguros identifica el archivo como malintencionado**: se recomienda no habilitar esta opción.</span><span class="sxs-lookup"><span data-stu-id="34261-116">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="34261-117">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="34261-117">When you're finished, click **Save**.</span></span>

![Página de datos adjuntos seguros de ATP](../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-safe-documents"></a><span data-ttu-id="34261-119">Usar Exchange Online PowerShell o Exchange Online Protection PowerShell para configurar documentos seguros</span><span class="sxs-lookup"><span data-stu-id="34261-119">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="34261-120">Use la sintaxis que se muestre a continuación:</span><span class="sxs-lookup"><span data-stu-id="34261-120">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- <span data-ttu-id="34261-121">El parámetro _EnableSafeDocs_ habilita o deshabilita los documentos seguros para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="34261-121">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="34261-122">El parámetro _AllowSafeDocsOpen_ permite o impide que los usuarios abandonen la vista protegida (es decir, que abra el documento) si el documento se ha identificado como malintencionado.</span><span class="sxs-lookup"><span data-stu-id="34261-122">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="34261-123">En este ejemplo se habilitan documentos seguros para toda la organización y se impide que los usuarios abran documentos que se han identificado como malintencionados desde la vista protegida.</span><span class="sxs-lookup"><span data-stu-id="34261-123">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="34261-124">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="34261-124">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="34261-125">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="34261-125">How do I know this worked?</span></span>

<span data-ttu-id="34261-126">Para comprobar que ha habilitado y configurado documentos seguros, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="34261-126">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="34261-127">En el centro de seguridad & cumplimiento, vaya a la **Directiva** \> de **Administración** \> de amenazas **datos adjuntos seguros de ATP**y compruebe que las selecciones en la sección **ayuda para que los usuarios sigan siendo seguros cuando confíen en un archivo para abrir una vista protegida externa en la sección aplicaciones de Office** .</span><span class="sxs-lookup"><span data-stu-id="34261-127">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="34261-128">Ejecute el siguiente comando en Exchange Online PowerShell y compruebe los valores de propiedad:</span><span class="sxs-lookup"><span data-stu-id="34261-128">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
