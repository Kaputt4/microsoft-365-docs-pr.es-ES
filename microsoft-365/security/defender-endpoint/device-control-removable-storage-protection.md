---
title: Microsoft Defender para punto de conexión Device Control Removable Storage Protection
description: Comprender las "funcionalidades que ayudan a evitar que el usuario o la máquina o ambos usen medios de almacenamiento extraíbles no autorizados
keywords: medios de almacenamiento extraíbles
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3d679cfa4f09b06e2c7923ee1fe6e47247d90f76
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665082"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender para punto de conexión Device Control Removable Storage Protection


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

La protección de almacenamiento extraíble del control de dispositivos en Microsoft Defender para punto de conexión impide que los usuarios, los puntos de conexión o ambos usen medios de almacenamiento extraíbles no autorizados.

## <a name="protection-policies"></a>Directivas de protección

### <a name="removable-storage-access-control"></a>Control de acceso de almacenamiento extraíble

**Capabilities**

- *Auditoría* Lectura, escritura o ejecución del acceso al almacenamiento extraíble en función de varias propiedades de dispositivo, con o sin exclusión.
- *Prevenir* Lectura o escritura o ejecución del acceso con o sin exclusión: permitir un dispositivo específico basado en varias propiedades de dispositivo.

**detalles de soporte técnico de Windows 10 y Windows 11**:

- Se aplica en el nivel de dispositivo, en el nivel de usuario. o ambos. Permitir solo a personas específicas que realicen acceso de lectura, escritura y ejecución a un almacenamiento extraíble específico en una máquina específica.
- Compatibilidad con MEM OMA-URI y GPO.
- Se admiten "[Propiedades del dispositivo](#device-properties)" como se muestra en la lista.
- Para obtener la característica de Windows, consulte [Access Control de almacenamiento extraíble](device-control-removable-storage-access-control.md).

**Plataforma compatible**: Windows 10, Windows 11

**Detalles de soporte técnico de macOS**:

- Aplicado en el nivel de dispositivo: se aplica la misma directiva para cualquier usuario que haya iniciado sesión.
- Para obtener información específica de macOS, consulte [Control de dispositivos para macOS](mac-device-control-overview.md).

**Plataforma compatible:** macOS Catalina 10.15.4+ (con las extensiones del sistema habilitadas)


### <a name="device-installation"></a>Instalación del dispositivo

**Capacidades** : impedir la instalación con o sin exclusión en función de varias propiedades del dispositivo.

**detalles de soporte técnico de Windows 10 y Windows 11**:

- Aplicado en el nivel de dispositivo: se aplica la misma directiva para cualquier usuario que haya iniciado sesión.
- Admite objetos Microsoft Endpoint Manager y directiva de grupo.
- Se admiten "[Propiedades del dispositivo](#device-properties)" como se muestra en la lista.
- Para obtener más información sobre Windows, consulte [Control de dispositivos USB y otros medios extraíbles mediante Microsoft Defender para punto de conexión](control-usb-devices-using-intune.md).

**Plataforma compatible**: Windows 10, Windows 11

**Detalles de soporte técnico de macOS**:

- Aplicado en el nivel de dispositivo: se aplica la misma directiva para cualquier usuario que haya iniciado sesión.
- Para obtener información específica de macOS, consulte [Control de dispositivos para macOS](mac-device-control-overview.md).

**Plataforma compatible:** macOS Catalina 10.15.4+ (con las extensiones del sistema habilitadas) o posterior

### <a name="endpoint-dlp-removable-storage"></a>Almacenamiento extraíble dlp de punto de conexión

**Funcionalidades:** audite, advierta o impida que un usuario copie un elemento o información en un medio extraíble o un dispositivo USB.

**Descripción**: para obtener más información sobre Windows, consulte [Información sobre Microsoft 365 prevención de pérdida de datos de punto de conexión](../../compliance/endpoint-dlp-learn-about.md).

**Plataforma compatible**: Windows 10, Windows 11

### <a name="bitlocker"></a>BitLocker

**Funcionalidades**:

- Bloquee los datos que se van a escribir en unidades extraíbles que no estén protegidas por BitLocker.
- Bloquear el acceso a unidades extraíbles a menos que se cifren en un equipo propiedad de la organización

**Descripción**: para obtener más información sobre Windows, vea [BitLocker : Configuración de unidad extraíble](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).

**Plataforma compatible**: Windows 10, Windows 11

## <a name="device-properties"></a>Propiedades de dispositivo

Microsoft Defender para punto de conexión Device Control Removable Storage Protection permite restringir el acceso de almacenamiento extraíble en función de las propiedades descritas en la tabla siguiente:

<br/><br/>

|Nombre de la propiedad|Directivas aplicables|Se aplica a los sistemas operativos|Descripción|
|---|---|---|---|
|Clase de dispositivo|[Cómo controlar dispositivos USB y otros medios extraíbles mediante Microsoft Defender para punto de conexión](control-usb-devices-using-intune.md)|Windows|Para obtener información sobre los formatos de id. de dispositivo, consulte [clase de configuración de dispositivo](/windows-hardware/drivers/install/overview-of-device-setup-classes). Los dos vínculos siguientes proporcionan la lista completa de clases de configuración de dispositivos. Las clases "Uso del sistema" se refieren principalmente a los dispositivos que vienen con un equipo o equipo de fábrica, mientras que las clases "Vendor" se refieren principalmente a dispositivos que podrían estar conectados a un equipo o equipo existente: [Clases de configuración de dispositivos definidas por el sistema disponibles para proveedores: controladores de Windows](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors) y [clases de configuración de dispositivos definidas por el sistema reservadas para el uso del sistema: controladores Windows](/windows-hardware/drivers/install/system-defined-device-setup-classes-reserved-for-system-use). **Nota**: La instalación de dispositivos se puede aplicar a cualquier dispositivo, no solo al almacenamiento extraíble.|
|Identificador principal|[Almacenamiento extraíble Access Control](device-control-removable-storage-access-control.md)|Windows|El identificador principal incluye almacenamiento extraíble y CD/DVD y Windows dispositivo portátil/WPD.|
|Id. de dispositivo|[Almacenamiento extraíble Access Control](device-control-removable-storage-access-control.md); <p> [Cómo controlar dispositivos USB y otros medios extraíbles mediante Microsoft Defender para punto de conexión](control-usb-devices-using-intune.md)|Windows|Para obtener información sobre los formatos de id. de dispositivo, consulte [Identificadores USB estándar](/windows-hardware/drivers/install/standard-usb-identifiers), por ejemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07|
|Id. de hardware|[Almacenamiento extraíble Access Control](device-control-removable-storage-access-control.md) <p> [Cómo controlar dispositivos USB y otros medios extraíbles mediante Microsoft Defender para punto de conexión](control-usb-devices-using-intune.md)|Windows|Una cadena identificó el dispositivo en el sistema, por ejemplo, USBSTOR\DiskGeneric_Flash_Disk___8.07; **Nota**: El identificador de hardware no es único; diferentes dispositivos pueden compartir el mismo valor.|
|Id. de instancia|[Almacenamiento extraíble Access Control](device-control-removable-storage-access-control.md) <p> Instalación de dispositivo|Windows|Una cadena identifica de forma única el dispositivo en el sistema, por ejemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0|
|Nombre descriptivo|[Almacenamiento extraíble Access Control](device-control-removable-storage-access-control.md)|Windows|Cadena conectada al dispositivo, por ejemplo, dispositivo USB de disco flash genérico|
|Id. de proveedor/Id. de producto|[Almacenamiento extraíble Access Control](device-control-removable-storage-access-control.md)|Windows <p> macOS|Id. de proveedor es el código de proveedor de cuatro dígitos que el comité USB asigna al proveedor. Id. de producto es el código de producto de cuatro dígitos que el proveedor asigna al dispositivo; Carácter comodín de soporte técnico.|
|Número de serieId|[Almacenamiento extraíble Access Control](device-control-removable-storage-access-control.md)|Windows <p> macOS |Por ejemplo: `<SerialNumberId>002324B534BCB431B000058A</SerialNumberId>`|
