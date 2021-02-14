---
title: Desactivar la sincronización de directorios para Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: En este artículo, busque información sobre el uso de PowerShell para desactivar la sincronización de directorios para Microsoft 365.
ms.openlocfilehash: 0bd8591f91dcf20cb1061b3cd93f69511027bab1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693596"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="f68da-103">Desactivar la sincronización de directorios para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f68da-103">Turn off directory synchronization for Microsoft 365</span></span>
<span data-ttu-id="f68da-104">Puede usar PowerShell para desactivar la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="f68da-104">You can use PowerShell to turn off directory synchronization.</span></span> <span data-ttu-id="f68da-105">Sin embargo, no se recomienda desactivar la sincronización de directorios como paso de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="f68da-105">However, it is not recommended that you turn off directory synchronization as a troubleshooting step.</span></span> <span data-ttu-id="f68da-106">Si necesita ayuda para solucionar problemas de sincronización de directorios, consulte el artículo Solucionar problemas con la sincronización de directorios [para Microsoft 365.](fix-problems-with-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="f68da-106">If you need assistance with troubleshooting directory synchronization, see the [Fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) article.</span></span> 
  
<span data-ttu-id="f68da-107">[Póngase en contacto con](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) el soporte técnico de productos empresariales si es necesario.</span><span class="sxs-lookup"><span data-stu-id="f68da-107">[Contact support](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) for business products if needed.</span></span>
  
## <a name="turn-off-directory-synchronization"></a><span data-ttu-id="f68da-108">Desactivar la sincronización de directorios</span><span class="sxs-lookup"><span data-stu-id="f68da-108">Turn off directory synchronization</span></span>  
<span data-ttu-id="f68da-109">Para desactivar la sincronización de directorios:</span><span class="sxs-lookup"><span data-stu-id="f68da-109">To turn off Directory synchronization:</span></span>
  
1. <span data-ttu-id="f68da-110">En primer lugar, instale el software necesario y conéctese a su suscripción a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f68da-110">First, install the required software and connect to your Microsoft 365 subscription.</span></span> <span data-ttu-id="f68da-111">Para obtener instrucciones, [consulte Conectarse con el módulo microsoft Azure Active Directory para Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="f68da-111">For instructions, see [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
2. <span data-ttu-id="f68da-112">Use [Set-MsolDirSyncEnabled para](https://go.microsoft.com/fwlink/p/?LinkId=821939) deshabilitar la sincronización de directorios:</span><span class="sxs-lookup"><span data-stu-id="f68da-112">Use [Set-MsolDirSyncEnabled](https://go.microsoft.com/fwlink/p/?LinkId=821939) to disable directory synchronization:</span></span> 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
><span data-ttu-id="f68da-113">Si usa este comando, debe esperar 72 horas para volver a activar la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="f68da-113">If you use this command, you must wait 72 hours before you can turn directory synchronization back on.</span></span>
>
 
