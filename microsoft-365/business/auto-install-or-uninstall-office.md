---
title: Instalar o desinstalar automáticamente Office en dispositivos Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: 'Instale o desinstale Office en dispositivos Windows 10 desde el centro de administración empresarial de Microsoft 365. '
ms.openlocfilehash: fef4a543aed489202bf05dfb1e8cafbb784ca819
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277306"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a><span data-ttu-id="cf203-103">Instalar o desinstalar automáticamente Office en dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="cf203-103">Automatically install or uninstall Office on Windows 10 devices</span></span>

<span data-ttu-id="cf203-104">Puede instalar Office rápida y fácilmente en equipos Windows 10 desde el centro de administración de Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="cf203-104">You can quickly and easily install Office to Windows 10 PCs from the Microsoft 365 Business admin center.</span></span>
  
<span data-ttu-id="cf203-105">Para entender cómo funciona con aplicaciones de Office instaladas anteriormente, lea [Preparar la instalación del cliente de Office](prepare-for-office-client-deployment.md) antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="cf203-105">To understand how this works with previously installed Office apps, read [Prepare for Office client installation](prepare-for-office-client-deployment.md) before you get started.</span></span> 
  
## <a name="manage-office-deployments"></a><span data-ttu-id="cf203-106">Administrar implementaciones de Office</span><span class="sxs-lookup"><span data-stu-id="cf203-106">Manage Office deployments</span></span>

1. <span data-ttu-id="cf203-107">Inicie sesión en el [centro de administración](https://aka.ms/bcsportal) con credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="cf203-107">Sign in to the [admin center](https://aka.ms/bcsportal) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="cf203-108">En la tarjeta **Dispositivos**, seleccione **Administrar la implementación de Office**.</span><span class="sxs-lookup"><span data-stu-id="cf203-108">On the **Devices** card, choose **Manage Office Deployment**.</span></span>
      <span data-ttu-id="cf203-109">Si no ve la tarjeta **acciones de dispositivo** , en la página **principal** del centro de administración, haga clic en **Agregar** (+) para agregarla a la Página principal de administración.</span><span class="sxs-lookup"><span data-stu-id="cf203-109">If you do not see the **Device actions** card, in the admin center **Home** page, click **Add** (+) to add it to your admin home.</span></span>
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. <span data-ttu-id="cf203-111">En el panel **Administrar la implementación de Office** que se abre, seleccione **Agregar un grupo** y después seleccione los grupos que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="cf203-111">On the **Manage Office deployment** pane that opens, choose **Add a group**, then select the groups you want use.</span></span>
    
4. <span data-ttu-id="cf203-112">Después de haber agregado el grupo o los grupos que quiera usar, en la lista desplegable **Acción de implementación**, seleccione **Instalar Office tan pronto como sea posible** o **Desinstalar Office**.</span><span class="sxs-lookup"><span data-stu-id="cf203-112">After you have added the group or groups you want to use, from the **Deployment Action** drop-down, select either **Install Office as soon as possible** or **Uninstall Office**.</span></span>
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. <span data-ttu-id="cf203-114">Elija **Siguiente** \> revise la configuración y luego elija **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="cf203-114">Choose **Next** \> review the settings and then choose **Confirm**.</span></span>
    
<span data-ttu-id="cf203-115">Se instalará automáticamente Office de 32 bits o se desinstalará en los dispositivos propiedad de usuarios especificados por el grupo o los grupos que usó.</span><span class="sxs-lookup"><span data-stu-id="cf203-115">A 32-bit Office will be automatically installed, or uninstalled in the devices owned by users specified by the group or groups you used.</span></span>
  
<span data-ttu-id="cf203-116">Para comprobarlo, puede abrir el Administrador de tareas en un equipo en que haya seleccionado que se instale Office y buscar el proceso Hacer clic y ejecutar de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="cf203-116">To verify you can open the Task Manager on a computer that was selected for an Office install and look for Microsoft Office Click-to-Run process.</span></span>
  


