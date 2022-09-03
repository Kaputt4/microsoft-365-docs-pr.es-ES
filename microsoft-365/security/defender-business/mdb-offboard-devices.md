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
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 055cd0e6e6f2d3279d028e2af210f40b62f329ee
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67598591"
---
# <a name="offboard-a-device-from-microsoft-defender-for-business"></a>Desconectar un dispositivo de Microsoft Defender para Empresas

Si desea desconectar un dispositivo, use uno de los procedimientos siguientes:

- [Offboard a Windows device](#offboard-a-windows-device)
- [Offboard a Mac](#offboard-a-mac)

## <a name="offboard-a-windows-device"></a>Offboard a Windows device

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Configuración** y, a continuación, elija **Puntos de conexión**.

3. En **Administración de dispositivos**, elige **Desincorporación**.

4. Seleccione un sistema operativo, como **Windows 10 y 11** y, a continuación, en **Desincorporar un dispositivo**, en la sección **Método**, elige **Script local**. 

5. En la pantalla de confirmación, revise la información y elija **Descargar** para continuar.

6. Seleccione **Descargar paquete de retirada**. Se recomienda guardar el paquete de retirada en una unidad extraíble.

7. Ejecute el script en cada dispositivo que quiera desincorporar.

## <a name="offboard-a-mac"></a>Offboard a Mac

1. Vaya a **Aplicaciones finder** > . 

2. Haga clic con el botón derecho en **Microsoft Defender para Empresas** y, a continuación, elija **Mover a la papelera**. <br/>--- o --- <br/> Use el siguiente comando: `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`.

> [!IMPORTANT]
> La desincorporación de un dispositivo hace que los dispositivos dejen de enviar datos a Defender para empresas. Sin embargo, los datos recibidos antes de la desincorporación se conservan durante un máximo de seis (6) meses.

## <a name="next-steps"></a>Pasos siguientes

- [Use el panel de Administración de vulnerabilidades de Microsoft Defender en Microsoft Defender para Empresas](mdb-view-tvm-dashboard.md)
- [Ver o editar directivas en Microsoft Defender para Empresas](mdb-view-edit-create-policies.md)
- [Administración de dispositivos en Microsoft Defender para Empresas](mdb-manage-devices.md)