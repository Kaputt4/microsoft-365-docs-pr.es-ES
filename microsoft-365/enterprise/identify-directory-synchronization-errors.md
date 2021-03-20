---
title: Ver errores de sincronización de directorios en Microsoft 365
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
- MBS150
- GPA150
ms.assetid: b4fc07a5-97ea-4ca6-9692-108acab74067
description: Obtenga información sobre cómo ver errores de sincronización de directorios y posibles correcciones en el Centro de administración de Microsoft 365.
ms.openlocfilehash: 76717fc158aa0cee47f784919f19a295378bbd5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907509"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a><span data-ttu-id="9d45e-103">Ver errores de sincronización de directorios en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d45e-103">View directory synchronization errors in Microsoft 365</span></span>

<span data-ttu-id="9d45e-104">Puede ver errores de sincronización de directorios en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d45e-104">You can view directory synchronization errors in the Microsoft 365 admin center.</span></span> <span data-ttu-id="9d45e-105">Solo se muestran los errores del objeto User.</span><span class="sxs-lookup"><span data-stu-id="9d45e-105">Only the User object errors are displayed.</span></span> <span data-ttu-id="9d45e-106">Para ver errores con PowerShell, vea [Identificar objetos con DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).</span><span class="sxs-lookup"><span data-stu-id="9d45e-106">To view errors with PowerShell, see [Identify objects with DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).</span></span>

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a><span data-ttu-id="9d45e-107">Ver errores de sincronización de directorios en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d45e-107">View directory synchronization errors in the Microsoft 365 admin center</span></span>

<span data-ttu-id="9d45e-108">Para ver los errores en el Centro de administración de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="9d45e-108">To view any errors in the Microsoft 365 admin center:</span></span>
  
1. <span data-ttu-id="9d45e-109">Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con una cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="9d45e-109">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with a global administrator account.</span></span> 
    
2. <span data-ttu-id="9d45e-110">En la **página principal,** verá la tarjeta **de administración de** usuarios.</span><span class="sxs-lookup"><span data-stu-id="9d45e-110">On the **Home** page, you'll see the **User management** card.</span></span> 
    
    ![La tarjeta de administración de usuarios en el Centro de administración de Microsoft 365](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. <span data-ttu-id="9d45e-112">En la tarjeta, elija **Sincronizar errores en** Azure AD **Connect** para ver los errores en la página Errores de **sincronización de** directorios.</span><span class="sxs-lookup"><span data-stu-id="9d45e-112">On the card, choose **Sync errors** under **Azure AD Connect** to see the errors on the **Directory sync errors** page.</span></span>   
    
    ![Un ejemplo de la página Errores de sincronización de directorios](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. <span data-ttu-id="9d45e-114">Elija cualquiera de los errores para mostrar el panel de detalles con información sobre el error y sugerencias sobre cómo solucionarlo.</span><span class="sxs-lookup"><span data-stu-id="9d45e-114">Choose any of the errors to display the details pane with information about the error and tips on how to fix it.</span></span>

   ![Ejemplo de los detalles de un error de sincronización de directorios](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
<span data-ttu-id="9d45e-116">Después de verlo, consulte [fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) to correct any identified issues.</span><span class="sxs-lookup"><span data-stu-id="9d45e-116">After viewing, see [fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) to correct any identified issues.</span></span>