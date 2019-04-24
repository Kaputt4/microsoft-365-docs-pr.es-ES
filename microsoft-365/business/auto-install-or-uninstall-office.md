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
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a>Instalar o desinstalar automáticamente Office en dispositivos Windows 10

Puede instalar Office rápida y fácilmente en equipos Windows 10 desde el centro de administración de Microsoft 365 Business.
  
Para entender cómo funciona con aplicaciones de Office instaladas anteriormente, lea [Preparar la instalación del cliente de Office](prepare-for-office-client-deployment.md) antes de empezar. 
  
## <a name="manage-office-deployments"></a>Administrar implementaciones de Office

1. Inicie sesión en el [centro de administración](https://aka.ms/bcsportal) con credenciales de administrador global. 
    
2. En la tarjeta **Dispositivos**, seleccione **Administrar la implementación de Office**.
      Si no ve la tarjeta **acciones de dispositivo** , en la página **principal** del centro de administración, haga clic en **Agregar** (+) para agregarla a la Página principal de administración.
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. En el panel **Administrar la implementación de Office** que se abre, seleccione **Agregar un grupo** y después seleccione los grupos que quiera usar.
    
4. Después de haber agregado el grupo o los grupos que quiera usar, en la lista desplegable **Acción de implementación**, seleccione **Instalar Office tan pronto como sea posible** o **Desinstalar Office**.
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. Elija **Siguiente** \> revise la configuración y luego elija **Confirmar**.
    
Se instalará automáticamente Office de 32 bits o se desinstalará en los dispositivos propiedad de usuarios especificados por el grupo o los grupos que usó.
  
Para comprobarlo, puede abrir el Administrador de tareas en un equipo en que haya seleccionado que se instale Office y buscar el proceso Hacer clic y ejecutar de Microsoft Office.
  


