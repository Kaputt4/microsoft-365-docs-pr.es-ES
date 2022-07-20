---
title: Usar esta guía paso a paso para agregar perfiles y dispositivos de AutoPilot
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.collection: ''
ms.localizationpriority: high
ms.date: 07/19/2022
ms.custom:
- MiniMaven
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
description: Aprenda a usar Windows AutoPilot para configurar nuevos dispositivos de Windows 10 para su empresa para que estén listos para su uso por parte de los empleados.
ms.openlocfilehash: 72a35557d3ab70c5e11f91f366b9cbe003b0c4c6
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2022
ms.locfileid: "66893263"
---
# <a name="use-this-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Usar esta guía paso a paso para agregar perfiles y dispositivos de AutoPilot

Puede usar Windows AutoPilot para configurar **nuevos** dispositivos de Windows 10 en su empresa para que estén listos para usar en cuanto se los proporcione a sus empleados.
  
## <a name="device-requirements"></a>Requisitos del dispositivo

Los dispositivos tienen que cumplir estos requisitos:
  
- Windows 10, versión 1703 o posterior

- Los nuevos dispositivos que no han pasado por una configuración rápida de Windows.

## <a name="use-the-setup-guide-to-add-devices-and-profiles"></a>Usar la guía de configuración para crear perfiles y dispositivos

Si todavía no ha creado grupos de dispositivos ni perfiles, la mejor forma de empezar es mediante la guía paso a paso. También puede [agregar dispositivos Autopilot](m365bp-create-and-edit-Autopilot-devices.md) y [asignarles perfiles](../admin/devices/create-and-edit-Autopilot-profiles.md) sin usar la guía.
  
1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. En el panel de navegación izquierdo, elija **Dispositivos** \> **AutoPilot**.

    ![En el Centro de administración, elija Dispositivos y, a continuación, AutoPilot.](../media/Autopilot.png)
  
3. En la página **AutoPilot**, pulse o haga clic en **Guía de inicio**.

    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
4. En la página **Cargar archivo .csv con la lista de dispositivos**, vaya a la ubicación donde tenga el archivo .CSV preparado y haga clic en **Abrir** \> **Siguiente**. El archivo debe tener tres encabezados:

    - Columna A: Número de serie del dispositivo
    - Columna B: Id. del producto de Windows
    - Columna C: Hash de hardware

Puede obtener esta información de su proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutopilotInfo) para generar un archivo CSV.

Para más información, vea [Device list CSV-file](../admin/misc/device-list.md) (Archivo CSV de lista de dispositivos). También puede descargar un archivo de ejemplo en la página **Upload .csv file with list of devices** (Cargar archivo .csv con la lista de dispositivos).

> [!NOTE]
> Este script usa WMI para recuperar las propiedades necesarias para que un cliente registre un dispositivo con Windows Autopilot. Tenga en cuenta que es normal que el archivo CSV resultante no recopile un valor de id. de producto (PKID) de Windows, ya que esto no es necesario para registrar un dispositivo y que PKID sea NULL en el CSV de salida está bien. Solo se rellenarán el número de serie y el hash de hardware.

5. En la página **Asignar un perfil**, puede seleccionar un perfil existente o crear uno nuevo. Si todavía no tiene ninguno, se le pedirá que cree uno.

    Un perfil es una colección de valores que puede aplicar a un solo dispositivo o un grupo de dispositivos.

    Las características predeterminadas son obligatorias y se configurarán automáticamente. Las características predeterminadas son:

    - Se omite el registro de OEM, OneDrive y Cortana.

    - Se crea la experiencia de inicio de sesión con la marca de la compañía.

    - Conectar los dispositivos a cuentas de Azure Active Directory e inscribirlos automáticamente para que los administre Microsoft 365 Empresa Premium.

    Para obtener más información, consulte [Acerca de la configuración de perfiles de AutoPilot](m365bp-Autopilot-profile-settings.md).

6. Las otras opciones son **Skip privacy settings** (Omitir la configuración de privacidad) y **Don't allow user to become the local admin** (No permitir que el usuario se convierta en administrador local). De manera predeterminada, se establecen ambas en **Desactivado**.

    Elija **Siguiente**.

7. La página **Ha terminado** indica que el perfil que ha creado (o elegido) se aplicará al grupo de dispositivos que ha creado cargando la lista de dispositivos. Esta configuración estará vigente cuando los usuarios del dispositivo inicien sesión de nuevo. Elija **Cerrar**.

## <a name="related-content"></a>Contenido relacionado

- [Acerca de la configuración de perfiles de AutoPilot](../business-premium/m365bp-Autopilot-profile-settings.md) (artículo)\
- [Opciones para proteger los dispositivos y los datos de la aplicación](../admin/devices/choose-device-security.md) (artículo)
- [Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)
