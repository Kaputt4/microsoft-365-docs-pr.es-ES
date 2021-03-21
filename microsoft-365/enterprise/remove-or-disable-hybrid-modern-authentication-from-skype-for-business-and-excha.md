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
ms.openlocfilehash: 9442ef3e19d0835bfd59f27ec425e36fd7dfcf7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927293"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a><span data-ttu-id="50a12-103">Quitar o deshabilitar la autenticación moderna híbrida de Skype Empresarial y Exchange</span><span class="sxs-lookup"><span data-stu-id="50a12-103">Removing or disabling Hybrid Modern Authentication from Skype for Business and Exchange</span></span>

<span data-ttu-id="50a12-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="50a12-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="50a12-105">Si ha habilitado la autenticación moderna híbrida (HMA) solo para encontrar que no es adecuado para el entorno actual, puede deshabilitar HMA.</span><span class="sxs-lookup"><span data-stu-id="50a12-105">If you've enabled Hybrid Modern Authentication (HMA) only to find it's unsuitable for your current environment, you can disable HMA.</span></span> <span data-ttu-id="50a12-106">En este artículo se explica cómo.</span><span class="sxs-lookup"><span data-stu-id="50a12-106">This article explains how.</span></span>
  
## <a name="who-is-this-article-for"></a><span data-ttu-id="50a12-107">¿Para quién es este artículo?</span><span class="sxs-lookup"><span data-stu-id="50a12-107">Who is this article for?</span></span>

<span data-ttu-id="50a12-108">Si ha habilitado la autenticación moderna en Skype Empresarial Online o local, y/o Exchange Online o local y ha encontrado que necesita deshabilitar HMA, estos pasos son para usted.</span><span class="sxs-lookup"><span data-stu-id="50a12-108">If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="50a12-109">Consulte el artículo '[Topologías](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)de Skype Empresarial compatibles con autenticación moderna' si está en Skype Empresarial Online o local, tiene una HMA de topología mixta y necesita ver las topologías admitidas antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="50a12-109">See the '[Skype for Business topologies supported with Modern Authentication](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)' article if you're in Skype for Business Online or On-premises, have a mixed-topology HMA, and need to look at supported topologies before you begin.</span></span>
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a><span data-ttu-id="50a12-110">Cómo deshabilitar la autenticación moderna híbrida (Exchange)</span><span class="sxs-lookup"><span data-stu-id="50a12-110">How to disable Hybrid Modern Authentication (Exchange)</span></span>

1. <span data-ttu-id="50a12-111">**Exchange local:** abra el Shell de administración de Exchange y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="50a12-111">**Exchange On-premises**: Open the Exchange Management Shell and run the following commands:</span></span> 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. <span data-ttu-id="50a12-112">**Exchange Online:** [conéctese a Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) con PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="50a12-112">**Exchange Online**: [Connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) with Remote PowerShell.</span></span> <span data-ttu-id="50a12-113">Ejecute el siguiente comando para convertir la marca  *OAuth2ClientProfileEnabled*  en "false":</span><span class="sxs-lookup"><span data-stu-id="50a12-113">Run the following command to turn your  *OAuth2ClientProfileEnabled*  flag to 'false':</span></span>

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a><span data-ttu-id="50a12-114">Cómo deshabilitar la autenticación moderna híbrida (Skype Empresarial)</span><span class="sxs-lookup"><span data-stu-id="50a12-114">How to disable Hybrid Modern Authentication (Skype for Business)</span></span>

1. <span data-ttu-id="50a12-115">**Skype Empresarial local:** ejecute los siguientes comandos en el Shell de administración de Skype Empresarial:</span><span class="sxs-lookup"><span data-stu-id="50a12-115">**Skype for Business On-premises**: Run the following commands in Skype for Business Management Shell:</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. <span data-ttu-id="50a12-116">**Skype Empresarial Online:** [conéctese a Skype Empresarial Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) con PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="50a12-116">**Skype for Business Online**: [Connect to Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) with Remote PowerShell.</span></span> <span data-ttu-id="50a12-117">Ejecute el siguiente comando para deshabilitar la autenticación moderna:</span><span class="sxs-lookup"><span data-stu-id="50a12-117">Run the following command to disable Modern Authentication:</span></span>

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

<span data-ttu-id="50a12-118">[Vuelva a vincular a la información general sobre autenticación moderna](hybrid-modern-auth-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="50a12-118">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) .</span></span> 
