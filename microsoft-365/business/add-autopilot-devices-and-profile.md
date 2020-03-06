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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Obtenga información sobre cómo usar Windows AutoPilot para configurar nuevos dispositivos con Windows 10 para su empresa para que estén listos para el uso de los empleados.
ms.openlocfilehash: 8449d5a3672a20b0cd1ba61bbda863073138c04c
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2020
ms.locfileid: "42550395"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Usar la guía paso a paso para agregar perfiles y dispositivos de AutoPilot

Puede usar Windows AutoPilot para configurar **nuevos** dispositivos con Windows 10 para su empresa para que estén listos para usarse cuando los entregue a sus empleados.
  
## <a name="device-requirements"></a>Requisitos del dispositivo

Los dispositivos deben cumplir estos requisitos:
  
- Windows 10, versión 1703 o posterior
    
- Nuevos dispositivos que no han estado a la vista rápida de Windows
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Usar la guía de configuración para crear perfiles y dispositivos

[![Etiqueta para informarle que el centro de administración está cambiando y puede encontrar más detalles en aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Si aún no ha creado grupos de dispositivos o perfiles, la mejor forma de empezar es usar la guía paso a paso. También puede [Agregar dispositivos](create-and-edit-autopilot-devices.md) y [asignarles perfiles](create-and-edit-autopilot-profiles.md) sin usar la guía. 
  
1. Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. En el panel de navegación izquierdo, elija **dispositivos** \> **AutoPilot**.

    ![En el centro de administración, elija dispositivos y, a continuación, AutoPilot.](../media/AutoPilot.png)
  
2. En la página **AutoPilot** , haga clic o pulse **Guía de inicio**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. En la página **Cargar archivo. csv con la lista de dispositivos** , vaya a la ubicación donde se ha preparado el. Archivo CSV y, a continuación, **abrir** \> **siguiente**. El archivo debe tener tres encabezados:
    
    - Columna A: Número de serie del dispositivo
    
    - Columna B: Id. del producto de Windows
    
    - Columna C: Hash de hardware
    
    Puede obtener esta información de su proveedor de hardware o puede usar el script de [PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para generar un archivo CSV. 
    
    Para más información, vea [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) (Archivo CSV de lista de dispositivos). También puede descargar un archivo de ejemplo en la página **Upload .csv file with list of devices** (Cargar archivo .csv con la lista de dispositivos). 
    
4. En la página **asignar un perfil** , puede elegir un perfil existente o crear uno nuevo. Si aún no tiene uno, se le pedirá que cree uno. 
    
    Un perfil es una colección de valores que puede aplicar a un solo dispositivo o un grupo de dispositivos.
    
    Las características predeterminadas son necesarias y se establecen automáticamente. Las características predeterminadas son:
    
    - Omitir el registro de Cortana, OneDrive y OEM.
    
    - Se crea la experiencia de inicio de sesión con la marca de la compañía.
    
    - Conectar los dispositivos a las cuentas de Azure Active Directory y inscribirlos automáticamente para que los administre Microsoft 365 Business.
    
    Para obtener más información, consulte [acerca de la configuración de perfiles de AutoPilot](autopilot-profile-settings.md). 
    
5. Las otras opciones son **Skip privacy settings** (Omitir la configuración de privacidad) y **Don't allow user to become the local admin** (No permitir que el usuario se convierta en administrador local). De manera predeterminada, se establecen ambas en **Desactivado**. 
    
    Elija **Siguiente**.
    
6. Ya **ha terminado** indica que el perfil que ha creado (o elegido) se aplicará al grupo de dispositivos que ha creado cargando la lista de dispositivos. La configuración se aplicará cuando los usuarios del dispositivo inicien sesión a continuación. Elija **Cerrar**.
    
