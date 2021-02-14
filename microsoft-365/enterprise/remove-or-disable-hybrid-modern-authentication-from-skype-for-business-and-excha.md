---
title: Quitar o deshabilitar la autenticación moderna híbrida de Skype Empresarial y Exchange
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: En este artículo se explica cómo quitar o deshabilitar la autenticación moderna híbrida de Skype Empresarial y Exchange.
ms.openlocfilehash: 70f62b9b2165464837aa1dea0e12854df116efe0
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547101"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a><span data-ttu-id="6fa87-103">Quitar o deshabilitar la autenticación moderna híbrida de Skype Empresarial y Exchange</span><span class="sxs-lookup"><span data-stu-id="6fa87-103">Removing or disabling Hybrid Modern Authentication from Skype for Business and Exchange</span></span>

<span data-ttu-id="6fa87-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="6fa87-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6fa87-105">Si ha habilitado la autenticación moderna híbrida (HM) solo para encontrar que no es adecuado para su entorno actual, puede deshabilitar HM.</span><span class="sxs-lookup"><span data-stu-id="6fa87-105">If you've enabled Hybrid Modern Authentication (HMA) only to find it's unsuitable for your current environment, you can disable HMA.</span></span> <span data-ttu-id="6fa87-106">En este artículo se explica cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="6fa87-106">This article explains how.</span></span>
  
## <a name="who-is-this-article-for"></a><span data-ttu-id="6fa87-107">¿Para quién es este artículo?</span><span class="sxs-lookup"><span data-stu-id="6fa87-107">Who is this article for?</span></span>

<span data-ttu-id="6fa87-108">Si ha habilitado la autenticación moderna en Skype Empresarial Online o local, y/o Exchange Online o local y ha encontrado que necesita deshabilitar HM, estos pasos son para usted.</span><span class="sxs-lookup"><span data-stu-id="6fa87-108">If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fa87-109">Consulte el artículo "Topologías de[Skype](https://technet.microsoft.com/library/mt803262.aspx)Empresarial compatibles con la autenticación moderna" si está en Skype Empresarial Online o local, tiene una HM de topología mixta y necesita ver las topologías compatibles antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="6fa87-109">See the '[Skype for Business topologies supported with Modern Authentication](https://technet.microsoft.com/library/mt803262.aspx)' article if you're in Skype for Business Online or On-premises, have a mixed-topology HMA, and need to look at supported topologies before you begin.</span></span>
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a><span data-ttu-id="6fa87-110">Cómo deshabilitar la autenticación moderna híbrida (Exchange)</span><span class="sxs-lookup"><span data-stu-id="6fa87-110">How to disable Hybrid Modern Authentication (Exchange)</span></span>

1. <span data-ttu-id="6fa87-111">**Exchange local:** abra el Shell de administración de Exchange y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="6fa87-111">**Exchange On-premises**: Open the Exchange Management Shell and run the following commands:</span></span> 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. <span data-ttu-id="6fa87-112">**Exchange Online:** [conéctese a Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) con PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="6fa87-112">**Exchange Online**: [Connect to Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) with Remote PowerShell.</span></span> <span data-ttu-id="6fa87-113">Ejecute el siguiente comando para convertir la marca  *OAuth2ClientProfileEnabled*  en "false":</span><span class="sxs-lookup"><span data-stu-id="6fa87-113">Run the following command to turn your  *OAuth2ClientProfileEnabled*  flag to 'false':</span></span>

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a><span data-ttu-id="6fa87-114">Cómo deshabilitar la autenticación moderna híbrida (Skype Empresarial)</span><span class="sxs-lookup"><span data-stu-id="6fa87-114">How to disable Hybrid Modern Authentication (Skype for Business)</span></span>

1. <span data-ttu-id="6fa87-115">**Skype Empresarial local:** ejecute los siguientes comandos en el Shell de administración de Skype Empresarial:</span><span class="sxs-lookup"><span data-stu-id="6fa87-115">**Skype for Business On-premises**: Run the following commands in Skype for Business Management Shell:</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. <span data-ttu-id="6fa87-116">**Skype Empresarial Online:** [conéctese a Skype Empresarial Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) con PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="6fa87-116">**Skype for Business Online**: [Connect to Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) with Remote PowerShell.</span></span> <span data-ttu-id="6fa87-117">Ejecute el siguiente comando para deshabilitar la autenticación moderna:</span><span class="sxs-lookup"><span data-stu-id="6fa87-117">Run the following command to disable Modern Authentication:</span></span>

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

<span data-ttu-id="6fa87-118">[Vuelva a vincular a la introducción a la autenticación moderna.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6fa87-118">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) .</span></span> 
  

