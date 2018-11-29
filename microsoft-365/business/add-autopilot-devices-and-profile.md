---
title: Usar la guía paso a paso para agregar perfiles y dispositivos de AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
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
description: Obtenga información sobre cómo utilizar el piloto automático de Windows para configurar nuevos dispositivos de Windows 10 para su negocio.
ms.openlocfilehash: 56225424125e9eed9f46867837c564aa5d1c4adc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871157"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Usar la guía paso a paso para agregar perfiles y dispositivos de AutoPilot

Puede usar Windows AutoPilot para configurar nuevos dispositivos de Windows 10 en su empresa para que estén listos para su uso productivo en cuanto se los proporcione a sus empleados.
  
## <a name="device-requirements"></a>Requisitos del dispositivo

Los dispositivos tienen que cumplir estos requisitos:
  
- Windows 10, versión 1703 o posteriores.
    
- Nuevos dispositivos que no hayan pasado por una configuración rápida de Windows.
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Usar la guía de configuración para crear perfiles y dispositivos

Si todavía no tiene perfiles ni grupos de dispositivos, la mejor forma de empezar es mediante la guía paso a paso, pero también se pueden [agregar dispositivos](create-and-edit-autopilot-devices.md) y [asignar perfiles](create-and-edit-autopilot-profiles.md) sin usar la guía. 
  
1. En el Centro de administración de Microsoft 365 Business, busque la tarjeta **Acciones de dispositivo** y elija **Implementar Windows con AutoPilot**.
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. En la página **Preparar Windows**, pulse o haga clic en **Guía de inicio**.
    
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
    