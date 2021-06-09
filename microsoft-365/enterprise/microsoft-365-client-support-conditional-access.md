---
title: 'Microsoft 365 Compatibilidad con aplicaciones cliente: acceso condicional'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: En este artículo, obtenga información sobre qué plataformas, clientes y módulos de PowerShell admiten las aplicaciones Access para Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7b0b65ea25091aad01fd8741f9925f2b545e9c4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904971"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a><span data-ttu-id="7c696-103">Microsoft 365 Compatibilidad con aplicaciones cliente: acceso condicional</span><span class="sxs-lookup"><span data-stu-id="7c696-103">Microsoft 365 Client App Support: Conditional Access</span></span>

<span data-ttu-id="7c696-104">En el lugar de trabajo moderno, los usuarios pueden obtener acceso a los recursos de su organización con varios dispositivos y aplicaciones desde cualquier lugar.</span><span class="sxs-lookup"><span data-stu-id="7c696-104">In the modern workplace, users can access your organization's resources using various devices and apps from anywhere.</span></span> <span data-ttu-id="7c696-105">Como resultado, ya no basta con centrarse en quién puede obtener acceso a un recurso.</span><span class="sxs-lookup"><span data-stu-id="7c696-105">As a result, just focusing on who can access a resource is not sufficient anymore.</span></span> <span data-ttu-id="7c696-106">La organización también debe admitir cómo y dónde se tiene acceso a un recurso en la infraestructura de control de acceso.</span><span class="sxs-lookup"><span data-stu-id="7c696-106">Your organization must also support how and where a resource is accessed in your access control infrastructure.</span></span>

<span data-ttu-id="7c696-107">Con Azure Active Directory, ubicación y acceso condicional basado en autenticación multifactor, puedes cumplir este nuevo requisito.</span><span class="sxs-lookup"><span data-stu-id="7c696-107">With Azure Active Directory device, location, and multi-factor authentication-based Conditional Access, you can meet this new requirement.</span></span> <span data-ttu-id="7c696-108">El acceso condicional es una funcionalidad de Azure Active Directory que te permite aplicar controles en el acceso a las aplicaciones de tu entorno, todo en función de condiciones específicas y administrados desde una ubicación central.</span><span class="sxs-lookup"><span data-stu-id="7c696-108">Conditional Access is a capability of Azure Active Directory that enables you to enforce controls on the access to apps in your environment, all based on specific conditions and managed from a central location.</span></span>

<span data-ttu-id="7c696-109">Obtenga más información [sobre Azure Active Directory acceso condicional](/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="7c696-109">Learn more about [Azure Active Directory Conditional Access](/azure/active-directory/conditional-access/).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="7c696-110">Clientes compatibles & plataformas</span><span class="sxs-lookup"><span data-stu-id="7c696-110">Supported clients & platforms</span></span>

<span data-ttu-id="7c696-111">Las versiones más recientes de los siguientes clientes y plataformas admiten el acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="7c696-111">The latest versions of the following clients and platforms support conditional access.</span></span> <span data-ttu-id="7c696-112">Para obtener más información acerca de la compatibilidad de plataforma Microsoft 365, vea [Requisitos del](/microsoft-365/microsoft-365-and-office-resources)sistema para Microsoft 365 .</span><span class="sxs-lookup"><span data-stu-id="7c696-112">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Conditional access services support table](../includes/microsoft-365-client-support-conditional-access-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="7c696-113">Módulos de PowerShell compatibles</span><span class="sxs-lookup"><span data-stu-id="7c696-113">Supported PowerShell modules</span></span>

- [<span data-ttu-id="7c696-114">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c696-114">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="7c696-115">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c696-115">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="7c696-116">PowerShell de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7c696-116">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
