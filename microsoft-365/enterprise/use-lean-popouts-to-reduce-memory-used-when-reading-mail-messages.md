---
title: Usar popouts lean para reducir la memoria usada al leer mensajes de correo
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: Este artículo contiene información sobre el uso de elementos emergentes lean para mejorar el rendimiento de descarga de mensajes Outlook en la web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925261"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a><span data-ttu-id="c2516-103">Usar popouts lean para reducir la memoria usada al leer mensajes de correo</span><span class="sxs-lookup"><span data-stu-id="c2516-103">Use lean popouts to reduce memory used when reading mail messages</span></span>

<span data-ttu-id="c2516-104">Este artículo contiene información para mejorar el rendimiento de descarga de mensajes Outlook en la web.</span><span class="sxs-lookup"><span data-stu-id="c2516-104">This article contains information for improving message download performance in Outlook on the web.</span></span> <span data-ttu-id="c2516-105">Este artículo forma parte del plan de red y el ajuste del rendimiento [para Office 365](./network-planning-and-performance.md) proyecto.</span><span class="sxs-lookup"><span data-stu-id="c2516-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
  
<span data-ttu-id="c2516-106">Como administrador global de Office 365, puede configurar Outlook en la web para ofrecer _popouts_ lean, una versión más pequeña y con menos memoria de determinados mensajes de correo electrónico en Microsoft Edge o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="c2516-106">As an Office 365 global administrator, you can configure Outlook on the web to deliver _lean popouts_, a smaller, less memory-intensive version of certain email messages in Microsoft Edge or Internet Explorer.</span></span> <span data-ttu-id="c2516-107">Cuando se configuran popouts lean para Outlook en la web, se cargan componentes representados del lado servidor que optimizan el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c2516-107">When lean popouts are configured for Outlook on the web, server-side rendered components are loaded that optimize performance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c2516-108">A partir de marzo de 2018, los elementos emergentes lean no están disponibles para los mensajes que especifican restricciones de derechos de uso, como Information Rights Management (IRM).</span><span class="sxs-lookup"><span data-stu-id="c2516-108">As of March 2018, lean popouts are not available for messages that specify usage rights restrictions, such as Information Rights Management (IRM).</span></span>
  
<span data-ttu-id="c2516-109">Estas características seguirán funcionando en la ventana principal, pero no están disponibles en los popouts lean:</span><span class="sxs-lookup"><span data-stu-id="c2516-109">These features will continue to work in the main window but are not available in lean popouts:</span></span>
  
- <span data-ttu-id="c2516-110">Complementos de Outlook</span><span class="sxs-lookup"><span data-stu-id="c2516-110">Outlook add-ins</span></span>
  
- <span data-ttu-id="c2516-111">Skype Empresarial presencia</span><span class="sxs-lookup"><span data-stu-id="c2516-111">Skype for Business presence</span></span>
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a><span data-ttu-id="c2516-112">Para configurar popouts lean para todos los usuarios de la Office 365 organización</span><span class="sxs-lookup"><span data-stu-id="c2516-112">To configure lean popouts for all users within your Office 365 organization</span></span>
  
1. <span data-ttu-id="c2516-113">[Conectar para Exchange Online con PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c2516-113">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
  
2. <span data-ttu-id="c2516-114">Ejecute el cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) con el parámetro LeanPopoutEnabled de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c2516-114">Run the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet with the LeanPopoutEnabled parameter as follows:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  <span data-ttu-id="c2516-115">Por ejemplo, para habilitar popouts lean para todos los usuarios de la organización:</span><span class="sxs-lookup"><span data-stu-id="c2516-115">For example, to enable lean popouts for all users in your organization:</span></span>
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  <span data-ttu-id="c2516-116">Para deshabilitar las ventanas emergentes lean para todos los usuarios de la organización:</span><span class="sxs-lookup"><span data-stu-id="c2516-116">To disable lean popouts for all users in your organization:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```