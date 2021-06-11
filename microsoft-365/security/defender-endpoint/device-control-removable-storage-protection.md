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
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c9b97c2157ba8090628af23b2ab54cf38f04d8c6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538392"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender para Endpoint Device Control Removable Storage Protection

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender para Endpoint Device Control Removable Storage Protection impide que el usuario o la máquina o ambos utilicen medios de almacenamiento extraíbles no autorizados.

## <a name="protection-policies"></a>Directivas de protección

### <a name="device-installation"></a>Instalación del dispositivo

**Funcionalidades:** impedir la instalación con o sin exclusión basada en varias propiedades del dispositivo.

**Descripción**
- Se aplica a nivel de máquina: se aplica la misma directiva para cualquier usuario que haya iniciado sesión.
- Admite MEM y GPO.
- Compatible con '[Propiedades de dispositivo](#device-properties)' como se muestra.
- Para obtener más información Windows, vea [How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).

**Plataforma compatible:** Windows 10

**Descripción**
- Se aplica a nivel de máquina: se aplica la misma directiva para cualquier usuario que haya iniciado sesión
- Para obtener información específica de macOS, consulta [Control de dispositivos para macOS](mac-device-control-overview.md).
 
**Plataforma compatible:** macOS Catalina 10.15.4+ (con extensiones del sistema habilitadas)

### <a name="removable-storage-access-control"></a>Control de acceso de almacenamiento extraíble

**Capabilities**
- *Auditoría* Acceso de lectura o escritura o ejecución al almacenamiento extraíble basado en varias propiedades del dispositivo, con o sin exclusión.
- *Impedir* Acceso de lectura o escritura o ejecución con o sin exclusión: permitir un dispositivo específico basado en varias propiedades del dispositivo.

**Descripción**
- Se aplica a la máquina o al usuario o a ambos: solo permite a personas específicas que realizan lectura,escritura/ejecución acceder al almacenamiento extraíble específico en un equipo específico.
- Admite MEM OMA-URI y GPO.
- Compatible con '[Propiedades de dispositivo](#device-properties)' como se muestra.
- Para obtener información sobre la Windows, [consulte Control de acceso de almacenamiento extraíble](device-control-removable-storage-access-control.md).

**Plataforma compatible:** Windows 10

**Descripción**
- Se aplica a nivel de máquina: se aplica la misma directiva para cualquier usuario que haya iniciado sesión.
- Para obtener información específica de macOS, consulta [Control de dispositivos para macOS](mac-device-control-overview.md).
 
**Plataforma compatible:** macOS Catalina 10.15.4+ (con extensiones del sistema habilitadas)

### <a name="windows-portable-device-access-control"></a>Windows Control de acceso de dispositivo portátil

**Funcionalidades:** denegar el acceso de lectura o escritura a [cualquier Windows dispositivo](/windows-hardware/drivers/portable/)portátil , por ejemplo: Tableta, iPhone.

**Descripción**
- Se aplica a la máquina o al usuario o a ambos.
- Admite MEM OMA-URI y GPO.

**Plataforma compatible:** Windows 10

### <a name="endpoint-dlp-removable-storage"></a>Almacenamiento extraíble dlp de extremo

**Capacidades:** auditar o advertir o impedir que un usuario copie un elemento o información en medios extraíbles o dispositivo USB.

**Descripción:** para obtener más información sobre Windows, vea [Learn about Microsoft 365 Endpoint data loss prevention](../../compliance/endpoint-dlp-learn-about.md).

**Plataforma compatible:** Windows 10

### <a name="bitlocker"></a>BitLocker 

**Capabilities**
- Bloquee los datos que se escribirán en unidades extraíbles que no están BitLocker protegidas.
- Bloquear el acceso a unidades extraíbles a menos que estén cifradas en un equipo propiedad de su organización
 
**Descripción:** para obtener más información sobre Windows, vea [BitLocker – Removable Drive Configuración](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).

**Plataforma compatible:** Windows 10

## <a name="device-properties"></a>Propiedades del dispositivo

Microsoft Defender para Endpoint Device Control Removable Storage Protection le permite restringir el acceso de almacenamiento extraíble en función de las propiedades descritas en la tabla siguiente:


|Nombre de la propiedad  |Directivas aplicables  |Se aplica a sistemas operativos  |Descripción  |
|---------|---------|---------|---------|
|Clase device    |     [Cómo controlar dispositivos USB y otros medios extraíbles con Microsoft Defender para endpoint](control-usb-devices-using-intune.md)     |   Windows      |  Para obtener información acerca de los formatos de id. de dispositivo, consulta [clase de configuración del dispositivo](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors). **Nota:** La instalación del dispositivo se puede aplicar a cualquier dispositivo, no solo al almacenamiento extraíble.       |
|Id. principal   |     Control de acceso de almacenamiento extraíble    |   Windows      |      El identificador principal incluye almacenamiento extraíble y CD/DVD.   |
|Id. de dispositivo     |  [Cómo controlar dispositivos USB y otros medios extraíbles con Microsoft Defender para endpoint;](control-usb-devices-using-intune.md) Control de acceso de almacenamiento extraíble       |      Windows   |    Para obtener información sobre los formatos de id. de dispositivo, consulte [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers), por ejemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07      |
|Id. de hardware     |     [Cómo controlar dispositivos USB y otros medios extraíbles con Microsoft Defender para endpoint;](control-usb-devices-using-intune.md) Control de acceso de almacenamiento extraíble    |     Windows    |    Una cadena identificó el dispositivo en el sistema, por ejemplo, USBSTOR\DiskGeneric_Flash_Disk______8.07; **Nota:** El identificador de hardware no es único; diferentes dispositivos pueden compartir el mismo valor.|
|Id. de instancia    | Instalación de dispositivos; Control de acceso de almacenamiento extraíble     |     Windows    |   Una cadena identifica de forma única el dispositivo en el sistema, por ejemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0      |
|Nombre descriptivo     |     Control de acceso de almacenamiento extraíble    |   Windows      |    Una cadena adjunta al dispositivo, por ejemplo, Dispositivo USB de disco flash genérico     |
|Id. de proveedor /Id. de producto     |  Control de acceso de almacenamiento extraíble       |   Windows Mac      |     Id. de proveedor es el código de proveedor de cuatro dígitos que el comité USB asigna al proveedor. Id. de producto es el código de producto de cuatro dígitos que el proveedor asigna al dispositivo; Admite caracteres comodín.    |
|NumberId de serie     |     Control de acceso de almacenamiento extraíble    |      Windows Mac   |     Por ejemplo, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId>    |

## <a name="related-topic"></a>Tema relacionado

- [Control de dispositivo extraíble de Microsoft Defender para endpoint Storage control de acceso](device-control-removable-storage-access-control.md)

