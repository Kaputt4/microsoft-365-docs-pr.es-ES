---
title: Usar la guía paso a paso para agregar perfiles y dispositivos de AutoPilot
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Aprende a usar Windows AutoPilot para configurar nuevos dispositivos Windows 10 para tu empresa para que estén listos para el uso de los empleados.
ms.openlocfilehash: 75cc51b889f8673de8dba2357c777de47fd0d296
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913510"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Usar la guía paso a paso para agregar perfiles y dispositivos de AutoPilot

Puedes usar Windows AutoPilot para configurar nuevos dispositivos **Windows** 10 para tu empresa para que estén listos para usarlos cuando se los des a tus empleados.
  
## <a name="device-requirements"></a>Requisitos del dispositivo

Los dispositivos deben cumplir estos requisitos:
  
- Windows 10, versión 1703 o posterior
    
- Nuevos dispositivos que no han pasado por la experiencia personalizada de Windows
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Usar la guía de configuración para crear perfiles y dispositivos

[![Etiqueta para informarle que el centro de administración está cambiando y puede encontrar más detalles en aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](/office365/admin/microsoft-365-admin-center-preview)

Si aún no has creado grupos de dispositivos o perfiles, la mejor manera de empezar es usando la guía paso a paso. También puedes agregar [dispositivos y](create-and-edit-autopilot-devices.md) [asignarles perfiles](create-and-edit-autopilot-profiles.md) sin usar la guía. 
  
1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. En el panel de navegación izquierdo, elija **Dispositivos** \> **AutoPilot**.

    ![En el Centro de administración, elija dispositivos y, a continuación, AutoPilot.](../media/AutoPilot.png)
  
2. En la **página AutoPilot,** haga clic o pulse **en Guía de inicio**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared . CSV y, a **continuación, Abra** \> **Siguiente**. El archivo debe tener tres encabezados:
    
    - Columna A: Número de serie del dispositivo
    
    - Columna B: Id. del producto de Windows
    
    - Columna C: Hash de hardware
    
    Puede obtener esta información del proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para generar un archivo CSV. 
    
    Para más información, vea [Device list CSV-file](../admin/misc/device-list.md) (Archivo CSV de lista de dispositivos). También puede descargar un archivo de ejemplo en la página **Upload .csv file with list of devices** (Cargar archivo .csv con la lista de dispositivos). 
    
> [!NOTE]
> Este script usa WMI para recuperar las propiedades necesarias para que un cliente registre un dispositivo con Windows Autopilot. Ten en cuenta que es normal que el archivo CSV resultante no recopile un valor de Id. de producto de Windows (PKID), ya que esto no es necesario para registrar un dispositivo y PKID siendo NULL en el CSV de salida está totalmente bien. Solo se rellenarán el número de serie y el hash de hardware.
    
4. En la **página Asignar un perfil,** puede elegir un perfil existente o crear uno nuevo. Si aún no tiene uno, se le pedirá que cree uno. 
    
    Un perfil es una colección de valores que puede aplicar a un solo dispositivo o un grupo de dispositivos.
    
    Las características predeterminadas son necesarias y se establecen automáticamente. Las características predeterminadas son:
    
    - Omita el registro de Cortana, OneDrive y OEM.
    
    - Se crea la experiencia de inicio de sesión con la marca de la compañía.
    
    - Conecta tus dispositivos a cuentas de Azure Active Directory e inscríbalas automáticamente para que las administra Microsoft 365 Empresa Premium.
    
    Para obtener más información, vea [Acerca de la configuración de perfil de AutoPilot](autopilot-profile-settings.md). 
    
5. Las otras opciones son **Skip privacy settings** (Omitir la configuración de privacidad) y **Don't allow user to become the local admin** (No permitir que el usuario se convierta en administrador local). De manera predeterminada, se establecen ambas en **Desactivado**. 
    
    Elija **Siguiente**.
    
6. **Si has terminado,** indica que el perfil que creaste (o elegiste) se aplicará al grupo de dispositivos que creaste cargando la lista de dispositivos. La configuración estará en vigor cuando los usuarios del dispositivo inicien sesión a continuación. Elija **Cerrar**.
