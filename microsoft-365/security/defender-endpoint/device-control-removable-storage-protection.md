---
title: Microsoft Defender para Endpoint Device Control Removable Storage Protection
description: Comprender las "funcionalidades que ayudan a impedir que el usuario o la máquina o ambos utilicen medios de almacenamiento extraíbles no autorizados
keywords: medios de almacenamiento extraíbles
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 732fe4748db6f3a2f1d055ee900fa87e84de57ea
ms.sourcegitcommit: 251551539b1532fdac7b7e3dd2733a75c62e8a54
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2021
ms.locfileid: "58359990"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender para Endpoint Device Control Removable Storage Protection

[!INCLUDE [Prerelease](../includes/prerelease.md)]

La protección de almacenamiento extraíble del control de dispositivos en Microsoft Defender para extremo impide que los usuarios, los puntos de conexión o ambos utilicen medios de almacenamiento extraíbles no autorizados.

## <a name="protection-policies"></a>Directivas de protección

### <a name="removable-storage-access-control"></a>Control de acceso de almacenamiento extraíble

**Capabilities**

- *Auditoría* Acceso de lectura o escritura o ejecución al almacenamiento extraíble basado en varias propiedades del dispositivo, con o sin exclusión.
- *Impedir* Acceso de lectura o escritura o ejecución con o sin exclusión: permitir un dispositivo específico basado en varias propiedades del dispositivo.

**Windows 10 de soporte técnico:**

- Se aplica en el nivel de dispositivo, en el nivel de usuario. o ambos. Solo permitir que determinadas personas que realizan lectura/escritura/ejecución accedan al almacenamiento extraíble específico en un equipo específico.
- Admite MEM OMA-URI y GPO.
- Compatible con '[Propiedades de dispositivo](#device-properties)' como se muestra.
- Para obtener información sobre la Windows, [consulte Control de acceso de almacenamiento extraíble](device-control-removable-storage-access-control.md).

**Plataforma compatible:** Windows 10

**Detalles de soporte técnico de macOS:**

- Se aplica en el nivel de dispositivo: se aplica la misma directiva para cualquier usuario que haya iniciado sesión.
- Para obtener información específica de macOS, consulta [Control de dispositivos para macOS](mac-device-control-overview.md).

**Plataforma compatible:** macOS Catalina 10.15.4+ (con extensiones del sistema habilitadas)


### <a name="device-installation"></a>Instalación del dispositivo

**Funcionalidades:** impedir la instalación con o sin exclusión basada en varias propiedades del dispositivo.

**Windows 10 de soporte técnico:**

- Se aplica en el nivel de dispositivo: se aplica la misma directiva para cualquier usuario que haya iniciado sesión.
- Admite Microsoft Endpoint Manager y objetos de directiva de grupo.
- Compatible con '[Propiedades de dispositivo](#device-properties)' como se muestra.
- Para obtener más información Windows, vea [How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).

**Plataforma compatible:** Windows 10

**Detalles de soporte técnico de macOS:**

- Se aplica en el nivel de dispositivo: se aplica la misma directiva para cualquier usuario que haya iniciado sesión
- Para obtener información específica de macOS, consulta [Control de dispositivos para macOS](mac-device-control-overview.md).

**Plataforma compatible:** macOS Catalina 10.15.4+ (con extensiones del sistema habilitadas) o posterior

### <a name="endpoint-dlp-removable-storage"></a>Almacenamiento extraíble dlp de extremo

**Funcionalidades:** auditar, advertir o impedir que un usuario copie un elemento o información en medios extraíbles o dispositivos USB.

**Descripción:** para obtener más información sobre Windows, vea [Learn about Microsoft 365 Endpoint data loss prevention](../../compliance/endpoint-dlp-learn-about.md).

**Plataforma compatible:** Windows 10

### <a name="bitlocker"></a>BitLocker

**Funcionalidades**:

- Bloquee los datos que se escribirán en unidades extraíbles que no estén protegidas con BitLocker.
- Bloquear el acceso a unidades extraíbles a menos que estén cifradas en un equipo propiedad de su organización

**Descripción:** para obtener más información sobre Windows, vea [BitLocker - Removable Drive Configuración](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).

**Plataforma compatible:** Windows 10

## <a name="device-properties"></a>Propiedades de dispositivo

Microsoft Defender para Endpoint Device Control Removable Storage Protection le permite restringir el acceso de almacenamiento extraíble en función de las propiedades descritas en la tabla siguiente:

<br>

****

|Nombre de la propiedad|Directivas aplicables|Se aplica a sistemas operativos|Descripción|
|---------|---------|---------|---------|
|Clase device|- [Cómo controlar dispositivos USB y otros medios extraíbles con Microsoft Defender para endpoint](control-usb-devices-using-intune.md)|Windows|Para obtener información acerca de los formatos de id. de dispositivo, consulta [clase de configuración del dispositivo](/windows-hardware/drivers/install/overview-of-device-setup-classes). Los dos vínculos siguientes proporcionan la lista completa de clases de configuración de dispositivos. Las clases de "Uso del sistema" se refieren principalmente a dispositivos que vienen con un equipo o máquina de fábrica, mientras que las clases de "Proveedor" se refieren principalmente a dispositivos que podrían conectarse a un equipo o máquina existentes: Clases de configuración de dispositivos definidas por el sistema disponibles para proveedores - controladores de Windows y clases de configuración de dispositivos definidas por el sistema [reservadas](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors) para el uso del sistema [- controladores Windows](/windows-hardware/drivers/install/system-defined-device-setup-classes-reserved-for-system-use). **Nota:** La instalación del dispositivo se puede aplicar a cualquier dispositivo, no solo al almacenamiento extraíble.|
|Id. principal|- [Control de acceso de almacenamiento extraíble](device-control-removable-storage-access-control.md)|Windows|El identificador principal incluye almacenamiento extraíble y CD/DVD y Windows dispositivo portátil/WPD.|
|Id. de dispositivo|- [Control de acceso de almacenamiento extraíble;](device-control-removable-storage-access-control.md)</br>- [Cómo controlar dispositivos USB y otros medios extraíbles con Microsoft Defender para endpoint](control-usb-devices-using-intune.md)|Windows|Para obtener información sobre los formatos de id. de dispositivo, consulte [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers), por ejemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07|
|Id. de hardware|- [Control de acceso de almacenamiento extraíble;](device-control-removable-storage-access-control.md)</br>- [Cómo controlar dispositivos USB y otros medios extraíbles con Microsoft Defender para endpoint](control-usb-devices-using-intune.md)|Windows|Una cadena identificó el dispositivo en el sistema, por ejemplo, USBSTOR\DiskGeneric_Flash_Disk___8.07; **Nota:** El identificador de hardware no es único; diferentes dispositivos pueden compartir el mismo valor.|
|Id. de instancia|- [Control de acceso de almacenamiento extraíble;](device-control-removable-storage-access-control.md)</br>- Instalación de dispositivos|Windows|Una cadena identifica de forma única el dispositivo en el sistema, por ejemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0|
|Nombre descriptivo|- [Control de acceso de almacenamiento extraíble](device-control-removable-storage-access-control.md)|Windows|Una cadena adjunta al dispositivo, por ejemplo, Dispositivo USB de disco flash genérico|
|Id. de proveedor /Id. de producto|- [Control de acceso de almacenamiento extraíble](device-control-removable-storage-access-control.md)|Windows <br/> macOS |Id. de proveedor es el código de proveedor de cuatro dígitos que el comité USB asigna al proveedor. Id. de producto es el código de producto de cuatro dígitos que el proveedor asigna al dispositivo; Admite caracteres comodín.|
|NumberId de serie|- [Control de acceso de almacenamiento extraíble](device-control-removable-storage-access-control.md)|Windows <br/> macOS |Por ejemplo, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId>|

