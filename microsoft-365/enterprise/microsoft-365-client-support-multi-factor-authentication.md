---
title: 'Microsoft 365 Compatibilidad con aplicaciones cliente: autenticación multifactor'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: En este artículo, obtenga información sobre qué plataformas, clientes y módulos de PowerShell admiten la autenticación multifactor para Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 80ee370526d17d472cd048cd4d89b862e158b631
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927571"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a><span data-ttu-id="338a7-103">Microsoft 365 Compatibilidad con aplicaciones cliente: autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="338a7-103">Microsoft 365 Client App Support: Multi-factor authentication</span></span>

<span data-ttu-id="338a7-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="338a7-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="338a7-105">Para proporcionar un nivel adicional de seguridad para los inicios de sesión, los clientes pueden configurarse para usar la autenticación multifactor (MFA), que usa una contraseña de usuario y otro método de verificación de usuario basado en:</span><span class="sxs-lookup"><span data-stu-id="338a7-105">To provide an additional level of security for sign-ins, clients may be configured to use multi-factor authentication (MFA), which uses both a user password and another user verification method based on:</span></span>

- <span data-ttu-id="338a7-106">Algo en su poder que no se duplica fácilmente, como un teléfono inteligente.</span><span class="sxs-lookup"><span data-stu-id="338a7-106">Something  in their possession that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="338a7-107">Algo que el usuario tiene de forma única y biológica, como sus huellas digitales, rostro u otro atributo biométrico</span><span class="sxs-lookup"><span data-stu-id="338a7-107">Something the user has uniquely and biologically, such as their fingerprints, face, or other biometric attribute</span></span>

<span data-ttu-id="338a7-108">Obtenga más información [sobre la autenticación multifactor](/azure/active-directory/authentication/multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="338a7-108">Learn more about [multi-factor authentication](/azure/active-directory/authentication/multi-factor-authentication).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="338a7-109">Clientes compatibles & plataformas</span><span class="sxs-lookup"><span data-stu-id="338a7-109">Supported clients & platforms</span></span>

<span data-ttu-id="338a7-110">Las últimas versiones de los siguientes clientes y plataformas admiten la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="338a7-110">The latest versions of the following clients and platforms support multi-factor authentication.</span></span> <span data-ttu-id="338a7-111">Para obtener más información acerca de la compatibilidad de plataforma Microsoft 365, vea [Requisitos del](/microsoft-365/microsoft-365-and-office-resources)sistema para Microsoft 365 .</span><span class="sxs-lookup"><span data-stu-id="338a7-111">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Multi-factor authentication services support table](../includes/microsoft-365-client-support-modern-authentication-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="338a7-112">Módulos de PowerShell compatibles</span><span class="sxs-lookup"><span data-stu-id="338a7-112">Supported PowerShell modules</span></span>

- [<span data-ttu-id="338a7-113">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="338a7-113">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="338a7-114">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="338a7-114">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="338a7-115">PowerShell de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="338a7-115">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)