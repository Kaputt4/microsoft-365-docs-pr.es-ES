---
title: Instalar o desinstalar automáticamente Office en dispositivos Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: 'Instalar o desinstalar Office en dispositivos de Windows 10 desde el centro de administración de Microsoft 365 empresarial. '
ms.openlocfilehash: 997c001ed1520f1ac989255632d36f9b7bedd16c
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871587"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a>Instalar o desinstalar automáticamente Office en dispositivos Windows 10

Puede instalar Office rápida y fácilmente en equipos Windows 10 desde el centro de administración de Microsoft 365 Business.
  
Para entender cómo funciona con aplicaciones de Office instaladas anteriormente, lea [Preparar la instalación del cliente de Office](prepare-for-office-client-deployment.md) antes de empezar. 
  
## <a name="manage-office-deployments"></a>Administrar implementaciones de Office

1. Inicie sesión en el [centro de administración](https://aka.ms/bcsportal) con credenciales de administrador global. 
    
2. En la tarjeta de **dispositivos** , elija **Administrar la implementación de Office**.    Si no ve la ficha **Acciones del dispositivo** , en la página **principal** del centro de administración, haga clic en **Agregar** (+) para agregarlo a la página principal de administración.
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. En el panel **Administrar la implementación de Office** que se abre, seleccione **Agregar un grupo** y después seleccione los grupos que quiera usar.
    
4. Después de haber agregado el grupo o los grupos que quiera usar, en la lista desplegable **Acción de implementación**, seleccione **Instalar Office tan pronto como sea posible** o **Desinstalar Office**.
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. Elija **Siguiente** \> revise la configuración y luego elija **Confirmar**.
    
Se instalará automáticamente Office de 32 bits o se desinstalará en los dispositivos propiedad de usuarios especificados por el grupo o los grupos que usó.
  
Para comprobarlo, puede abrir el Administrador de tareas en un equipo en que haya seleccionado que se instale Office y buscar el proceso Hacer clic y ejecutar de Microsoft Office.
  


