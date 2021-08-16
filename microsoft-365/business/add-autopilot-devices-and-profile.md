---
title: Usar la guía paso a paso para agregar perfiles y dispositivos de AutoPilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Aprende a usar Windows AutoPilot para configurar nuevos dispositivos Windows 10 para tu empresa para que estén listos para el uso de los empleados.
ms.openlocfilehash: b61ece9a82e12bec088be1b8e2611a13ea7f80d7669911ccaa57df72bf75ee84
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53896466"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Usar la guía paso a paso para agregar perfiles y dispositivos de AutoPilot

Puedes usar Windows AutoPilot para configurar nuevos **dispositivos** Windows 10 para tu empresa para que estén listos para su uso cuando se los des a tus empleados.
  
## <a name="device-requirements"></a>Requisitos del dispositivo

Los dispositivos deben cumplir estos requisitos:
  
- Windows 10, versión 1703 o posterior
    
- Nuevos dispositivos que no han pasado por Windows experiencia lista para su uso
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Usar la guía de configuración para crear perfiles y dispositivos

Si aún no has creado grupos de dispositivos o perfiles, la mejor manera de empezar es usando la guía paso a paso. También puedes agregar [dispositivos y](create-and-edit-autopilot-devices.md) [asignarles perfiles](create-and-edit-autopilot-profiles.md) sin usar la guía. 
  
1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. En el panel de navegación izquierdo, elija **Dispositivos** \> **AutoPilot**.

    ![En el Centro de administración, elija dispositivos y, a continuación, AutoPilot.](../media/AutoPilot.png)
  
2. En la **página AutoPilot,** haga clic o pulse **en Guía de inicio**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. En la **Upload .csv archivo con lista** de dispositivos, vaya a una ubicación donde tenga el archivo de .CSV preparado y, a continuación, **Abra** \> **Siguiente**. El archivo debe tener tres encabezados:
    
    - Columna A: Número de serie del dispositivo
    
    - Columna B: Id. del producto de Windows
    
    - Columna C: Hash de hardware
    
    Puede obtener esta información del proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para generar un archivo CSV. 
    
    Para más información, vea [Device list CSV-file](../admin/misc/device-list.md) (Archivo CSV de lista de dispositivos). También puede descargar un archivo de ejemplo en la página **Upload .csv file with list of devices** (Cargar archivo .csv con la lista de dispositivos). 
    
> [!NOTE]
> Este script usa WMI para recuperar las propiedades necesarias para que un cliente registre un dispositivo con Windows Autopilot. Tenga en cuenta que es normal que el archivo CSV resultante no recopile un valor de id. de producto (PKID) de Windows, ya que esto no es necesario para registrar un dispositivo y PKID siendo NULL en el CSV de salida está totalmente bien. Solo se rellenarán el número de serie y el hash de hardware.
    
4. En la **página Asignar un perfil,** puede elegir un perfil existente o crear uno nuevo. Si aún no tiene uno, se le pedirá que cree uno. 
    
    Un perfil es una colección de valores que puede aplicar a un solo dispositivo o un grupo de dispositivos.
    
    Las características predeterminadas son necesarias y se establecen automáticamente. Las características predeterminadas son:
    
    - Omita Cortana, OneDrive y registro OEM.
    
    - Se crea la experiencia de inicio de sesión con la marca de la compañía.
    
    - Conectar dispositivos para que Azure Active Directory cuentas y las inscriban automáticamente para que las administra Microsoft 365 Empresa Premium.
    
    Para obtener más información, vea [Acerca de la configuración de perfil de AutoPilot](autopilot-profile-settings.md). 
    
5. Las otras opciones son **Skip privacy settings** (Omitir la configuración de privacidad) y **Don't allow user to become the local admin** (No permitir que el usuario se convierta en administrador local). De manera predeterminada, se establecen ambas en **Desactivado**. 
    
    Elija **Siguiente**.
    
6. **Si has terminado,** indica que el perfil que creaste (o elegiste) se aplicará al grupo de dispositivos que creaste cargando la lista de dispositivos. La configuración estará en vigor cuando los usuarios del dispositivo inicien sesión a continuación. Elija **Cerrar**.

## <a name="related-content"></a>Contenido relacionado

[Acerca de la configuración de perfil de AutoPilot](autopilot-profile-settings.md) (artículo)\
[Opciones para proteger los dispositivos y los datos de la aplicación](../admin/devices/choose-device-security.md) (artículo)
