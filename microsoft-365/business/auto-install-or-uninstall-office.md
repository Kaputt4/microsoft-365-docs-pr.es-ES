---
title: Instalar o desinstalar automáticamente Office en dispositivos Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
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
ms.openlocfilehash: 1e962f51882ddfd97da566858a0a1e6fb56ecbb8
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071968"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a><span data-ttu-id="e1e18-103">Instalar o desinstalar automáticamente Office en dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="e1e18-103">Automatically install or uninstall Office on Windows 10 devices</span></span>

![Pancarta que apunta a https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

<span data-ttu-id="e1e18-105">Puede instalar Office rápida y fácilmente en equipos Windows 10 desde el centro de administración de Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="e1e18-105">You can quickly and easily install Office to Windows 10 PCs from the Microsoft 365 Business admin center.</span></span>
  
<span data-ttu-id="e1e18-106">Para entender cómo funciona con aplicaciones de Office instaladas anteriormente, lea [Preparar la instalación del cliente de Office](prepare-for-office-client-deployment.md) antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="e1e18-106">To understand how this works with previously installed Office apps, read [Prepare for Office client installation](prepare-for-office-client-deployment.md) before you get started.</span></span> 
  
## <a name="manage-office-deployments"></a><span data-ttu-id="e1e18-107">Administrar implementaciones de Office</span><span class="sxs-lookup"><span data-stu-id="e1e18-107">Manage Office deployments</span></span>

1. <span data-ttu-id="e1e18-108">Inicie sesión en el [centro de administración](https://aka.ms/bcsportal) con credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="e1e18-108">Sign in to the [admin center](https://aka.ms/bcsportal) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="e1e18-109">En la tarjeta **Dispositivos**, seleccione **Administrar la implementación de Office**.</span><span class="sxs-lookup"><span data-stu-id="e1e18-109">On the **Devices** card, choose **Manage Office Deployment**.</span></span>
      <span data-ttu-id="e1e18-110">Si no ve la tarjeta **acciones de dispositivo** , en la página **principal** del centro de administración, haga clic en **Agregar** (+) para agregarla a la Página principal de administración.</span><span class="sxs-lookup"><span data-stu-id="e1e18-110">If you do not see the **Device actions** card, in the admin center **Home** page, click **Add** (+) to add it to your admin home.</span></span>
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. <span data-ttu-id="e1e18-112">En el panel **Administrar la implementación de Office** que se abre, seleccione **Agregar un grupo** y después seleccione los grupos que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="e1e18-112">On the **Manage Office deployment** pane that opens, choose **Add a group**, then select the groups you want use.</span></span>
    
4. <span data-ttu-id="e1e18-113">Después de haber agregado el grupo o los grupos que quiera usar, en la lista desplegable **Acción de implementación**, seleccione **Instalar Office tan pronto como sea posible** o **Desinstalar Office**.</span><span class="sxs-lookup"><span data-stu-id="e1e18-113">After you have added the group or groups you want to use, from the **Deployment Action** drop-down, select either **Install Office as soon as possible** or **Uninstall Office**.</span></span>
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. <span data-ttu-id="e1e18-115">Elija **Siguiente** \> revise la configuración y luego elija **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e1e18-115">Choose **Next** \> review the settings and then choose **Confirm**.</span></span>
    
<span data-ttu-id="e1e18-116">Se instalará automáticamente Office de 32 bits o se desinstalará en los dispositivos propiedad de usuarios especificados por el grupo o los grupos que usó.</span><span class="sxs-lookup"><span data-stu-id="e1e18-116">A 32-bit Office will be automatically installed, or uninstalled in the devices owned by users specified by the group or groups you used.</span></span>
  
<span data-ttu-id="e1e18-117">Para comprobarlo, puede abrir el Administrador de tareas en un equipo en que haya seleccionado que se instale Office y buscar el proceso Hacer clic y ejecutar de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="e1e18-117">To verify you can open the Task Manager on a computer that was selected for an Office install and look for Microsoft Office Click-to-Run process.</span></span>
  


