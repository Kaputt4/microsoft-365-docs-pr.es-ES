---
title: Desconectar un dispositivo de Microsoft Defender para Empresas
description: Obtenga información sobre cómo quitar o desconectar un dispositivo de Microsoft Defender para Empresas.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 08/11/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security
- m365-initiative-defender-business
- tier1
ms.openlocfilehash: c87446bc9ce25287f2d615e72c11a56619742186
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804847"
---
# <a name="offboard-a-device-from-microsoft-defender-for-business"></a>Desconectar un dispositivo de Microsoft Defender para Empresas

A medida que los dispositivos se reemplazan o se retiran, o cambian las necesidades empresariales, puede quitar dispositivos de Defender para empresas. La retirada de un dispositivo hace que el dispositivo deje de enviar datos a Defender for Business. Sin embargo, los datos recibidos antes de la desincorporación se conservan durante un máximo de seis (6) meses.

> [!IMPORTANT]
> En los procedimientos de este artículo se describe cómo quitar un dispositivo de la supervisión por parte de Defender for Business. Si usa Microsoft Intune para administrar dispositivos y prefiere quitar el dispositivo de Intune, consulte [Eliminación de dispositivos mediante borrado, retirada o anulación manual de la inscripción del dispositivo](/mem/intune/remote-actions/devices-wipe).

## <a name="what-to-do"></a>Qué hacer

1. Seleccione una pestaña:

   - **Windows 10 o 11**
   - **Mac**
   - **Servidores** (Windows Server o Linux Server)
   - **Móvil** (para dispositivos iOS/iPadOS o Android)

2. Siga las instrucciones de la pestaña seleccionada.
3. Continúe con los pasos siguientes. 

## <a name="windows-10-or-11"></a>[**Windows 10 o 11**](#tab/Windows1011)

## <a name="windows-10-or-11"></a>Windows 10 u 11

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Configuración** y, a continuación, elija **Puntos de conexión**.

3. En **Administración de dispositivos**, elige **Desincorporación**.

4. Seleccione un sistema operativo, como **Windows 10 y 11** y, a continuación, en **Desincorporar un dispositivo**, en la sección **Método**, elige **Script local**. 

5. En la pantalla de confirmación, revise la información y elija **Descargar** para continuar.

6. Select **Download offboarding package**. We recommend saving the offboarding package to a removable drive.

7. Ejecute el script en cada dispositivo que quiera desincorporar.

## <a name="next-steps"></a>Pasos siguientes

- [Use el panel de Administración de vulnerabilidades de Microsoft Defender en Microsoft Defender para Empresas](mdb-view-tvm-dashboard.md)
- [Ver o editar directivas en Microsoft Defender para Empresas](mdb-view-edit-create-policies.md)
- [Administración de dispositivos en Microsoft Defender para Empresas](mdb-manage-devices.md)

## <a name="mac"></a>[**Mac**](#tab/mac)

## <a name="offboard-a-mac"></a>Offboard a Mac

1. Vaya a **Aplicaciones finder** > . 

2. Haga clic con el botón derecho en **Microsoft Defender para Empresas** y, a continuación, elija **Mover a la papelera**. <br/>--- o --- <br/> Use el siguiente comando: `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`.

## <a name="next-steps"></a>Pasos siguientes

- [Use el panel de Administración de vulnerabilidades de Microsoft Defender en Microsoft Defender para Empresas](mdb-view-tvm-dashboard.md)
- [Ver o editar directivas en Microsoft Defender para Empresas](mdb-view-edit-create-policies.md)
- [Administración de dispositivos en Microsoft Defender para Empresas](mdb-manage-devices.md)


## <a name="servers"></a>[**Servidores**](#tab/Servers)

## <a name="servers"></a>Servidores

Elija el sistema operativo del servidor:

- [Windows Server](#windows-server)
- [Servidor Linux](#linux-server)

### <a name="windows-server"></a>Windows Server

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija Settings **Endpoints (Puntos de conexión** de **configuración** > ) y, a continuación, en **Administración** de dispositivos, elija **Offboarding (Offboarding).**

3. Seleccione un sistema operativo, como **Windows Server 1803, 2019 y 2022**, y, a continuación, en la sección **Método de implementación** , elija **Script local**. 

4. Seleccione **Descargar paquete**. Se recomienda guardar el paquete de offboarding en una unidad extraíble. Se llamará a `WindowsDefenderATPOffboardingPackage_valid_until_YYYY-MM-DD.zip` la carpeta comprimida (donde `YYYY-MM-DD` es la fecha de expiración del paquete).

5. En el dispositivo Windows Server, extraiga el contenido de la carpeta comprimida en una ubicación como la carpeta Escritorio.  

6. Abra un símbolo del sistema como administrador.

7. Escriba la ubicación del archivo de script. Por ejemplo, si copió el archivo en la carpeta Escritorio, escribiría `%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_2022-11-11.cmd` (donde `YYYY-MM-DD` es la fecha de expiración del paquete) y, a continuación, presione Entrar (o seleccione **Aceptar**).

### <a name="linux-server"></a>Servidor Linux

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija Settings **Endpoints (Puntos de conexión** de **configuración** > ) y, a continuación, en **Administración** de dispositivos, elija **Offboarding (Offboarding).**

3. Seleccione **Servidor Linux** para el sistema operativo y, a continuación, en la sección **Método de implementación** , elija **Script local**. 

4. Seleccione **Descargar paquete**. Se recomienda guardar el paquete de offboarding en una unidad extraíble. Se llamará a `WindowsDefenderATPOffboardingPackage_valid_until_YYYY-MM-DD.zip` la carpeta comprimida (donde `YYYY-MM-DD` es la fecha de expiración del paquete).

5. En el dispositivo Linux Server, extraiga el contenido de la carpeta comprimida en una ubicación como la carpeta Escritorio.  

6. Abra un terminal y vaya al directorio donde se encuentra el `MicrosoftDefenderATPOffboardingLinuxServer_valid_until_YYYY-MM-DD` archivo (donde `YYYY-MM-DD` es la fecha de expiración del archivo).

7. Escriba `python MicrosoftDefenderATPOffboardingLinuxServer_valid_until_YYYY-MM-DD.py` en el terminal.

> [!TIP]
> Para obtener más información, vea [Desinstalar](../defender-endpoint/linux-resources.md) en la guía de Microsoft Defender para punto de conexión en Linux.

## <a name="next-steps"></a>Pasos siguientes

- [Use el panel de Administración de vulnerabilidades de Microsoft Defender en Microsoft Defender para Empresas](mdb-view-tvm-dashboard.md)
- [Ver o editar directivas en Microsoft Defender para Empresas](mdb-view-edit-create-policies.md)
- [Administración de dispositivos en Microsoft Defender para Empresas](mdb-manage-devices.md)

## <a name="mobile-devices"></a>[**Dispositivos móviles**](#tab/mobiles)

## <a name="mobile-devices"></a>Dispositivos móviles

Puede usar Microsoft Intune para administrar dispositivos móviles, como dispositivos iOS, iPadOS y Android.

Consulte [administración de dispositivos Microsoft Intune](/mem/intune/remote-actions/device-management).

## <a name="next-steps"></a>Pasos siguientes

- [Use el panel de Administración de vulnerabilidades de Microsoft Defender en Microsoft Defender para Empresas](mdb-view-tvm-dashboard.md)
- [Ver o editar directivas en Microsoft Defender para Empresas](mdb-view-edit-create-policies.md)
- [Administración de dispositivos en Microsoft Defender para Empresas](mdb-manage-devices.md)