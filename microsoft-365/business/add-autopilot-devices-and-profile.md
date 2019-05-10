---
title: Usar la guía paso a paso para agregar perfiles y dispositivos de AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Obtenga información sobre cómo usar Windows AutoPilot para configurar nuevos dispositivos con Windows 10 para su empresa.
ms.openlocfilehash: 8c4a14b4b9dcbf7a30c1e6e0bdd53418a1ab8a03
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660695"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Usar la guía paso a paso para agregar perfiles y dispositivos de AutoPilot

Puede usar Windows AutoPilot para configurar **nuevos** dispositivos con Windows 10 para su empresa para que estén listos para un uso productivo en cuanto los entregue a sus empleados.
  
## <a name="device-requirements"></a>Requisitos del dispositivo

Los dispositivos tienen que cumplir estos requisitos:
  
- Windows 10, versión 1703 o posteriores.
    
- Los nuevos dispositivos que no han pasado por una configuración rápida de Windows.
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Usar la guía de configuración para crear perfiles y dispositivos

![Pancarta que apunta a https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

Si todavía no tiene perfiles ni grupos de dispositivos, la mejor forma de empezar es mediante la guía paso a paso, pero también se pueden [agregar dispositivos](create-and-edit-autopilot-devices.md) y [asignar perfiles](create-and-edit-autopilot-profiles.md) sin usar la guía. 
  
1. Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. En el panel de navegación izquierdo, seleccione **dispositivos** \> **** de AutoPilot.

    ![En el centro de administración, elija dispositivos y, a continuación, AutoPilot.](media/AutoPilot.png)
  
2. En la **** página AutoPilot, haga clic o pulse **Guía de inicio**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. En la página **Upload .csv file with list of devices** (Cargar archivo .csv con la lista de dispositivos), vaya a la ubicación donde tenga el archivo .CSV preparado y haga clic en **Abrir** \> **Siguiente**. El archivo debe tener tres encabezados:
    
  - Columna A: Número de serie del dispositivo
    
  - Columna B: Id. del producto de Windows
    
  - Columna C: Hash de hardware
    
    Puede obtener esta información de su proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), que generará un archivo CSV. 
    
    Para más información, vea [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) (Archivo CSV de lista de dispositivos). También puede descargar un archivo de ejemplo en la página **Upload .csv file with list of devices** (Cargar archivo .csv con la lista de dispositivos). 
    
4. En la página **Assign a profile** (Asignar un perfil), puede seleccionar un perfil existente o crear uno. Si todavía no tiene ninguno, se le pedirá que cree uno. 
    
    Un perfil es una colección de valores que puede aplicar a un solo dispositivo o un grupo de dispositivos.
    
    Las características predeterminadas son obligatorias y se configurarán automáticamente. Las características predeterminadas son:
    
  - Se omite el registro de OEM, OneDrive y Cortana.
    
  - Se crea la experiencia de inicio de sesión con la marca de la compañía.
    
  - Los dispositivos estarán conectados a cuentas de Azure Active Directory e inscritos automáticamente para que Microsoft 365 Business los administre.
    
    Para obtener más información, vea:
    
    [Información sobre la configuración de los perfiles de AutoPilot](autopilot-profile-settings.md) . 
    
5. Las otras opciones son **Skip privacy settings** (Omitir la configuración de privacidad) y **Don't allow user to become the local admin** (No permitir que el usuario se convierta en administrador local). De manera predeterminada, se establecen ambas en **Desactivado**. 
    
    Elija **Siguiente**.
    
6. La página **Ha terminado** indica que el perfil que ha creado (o elegido) se aplicará al grupo de dispositivos que ha creado cargando la lista de dispositivos. Esta configuración estará vigente cuando los usuarios del dispositivo inicien la siguiente sesión. Elija **Cerrar**.
    