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
ms.openlocfilehash: ec5cfa78852d65db808c4e853f90f5639df25d6f
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300271"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender para Endpoint Device Control Removable Storage Protection

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender para Endpoint Device Control Removable Storage Protection impide que el usuario o la máquina o ambos utilicen medios de almacenamiento extraíbles no autorizados.

**Microsoft Defender para Endpoint Removable Storage Protection**


|Directiva  |Funcionalidad |Descripción  |
|---------|---------|---------|
|Instalación de dispositivos    |  Impedir la instalación con o sin exclusión: permitir dispositivos específicos basados en varias propiedades; Para obtener más información, consulta la [sección Propiedades del](#device-properties) dispositivo a continuación.        |    Funciona en el equipo: la misma directiva restringirá el inicio de sesión de diferentes usuarios en la misma máquina. Para obtener información, [vea How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).     |
|Control de acceso de almacenamiento extraíble      | (1) Auditar el acceso de lectura, escritura o ejecución al almacenamiento extraíble basado en varias propiedades del dispositivo, con o sin excepción. Para obtener más información, consulta la [sección Propiedades del](#device-properties) dispositivo a continuación. (2) Impedir el acceso de lectura, escritura o ejecución con o sin exclusión: permitir dispositivos específicos basados en varias propiedades del dispositivo; para obtener más información sobre las propiedades del dispositivo, consulta la [sección Propiedades del](#device-properties) dispositivo a continuación.     |     Funciona en una máquina o en un usuario o en ambos: solo permite que personas específicas que realizan lectura/escritura/ejecución accedan al almacenamiento extraíble específico en un equipo específico; para ver la característica Windows, vea [Control de acceso de almacenamiento extraíble;](device-control-removable-storage-access-control.md) para obtener información sobre la característica en Mac, consulta [Control de dispositivos para macOS](mac-device-control-overview.md).     |
|Almacenamiento extraíble dlp de extremo      |    Auditar o advertir o impedir que un usuario copie un elemento o información en medios extraíbles o dispositivo USB.     |  Para obtener más información, vea [Microsoft Endpoint DLP](/compliance/endpoint-dlp-learn-about.md).       |
|BitLocker    |     Bloquee los datos que se van a escribir en unidades extraíbles que no están protegidas BitLocker: bloquee el acceso a unidades extraíbles a menos que se cifraron en un equipo propiedad de su organización.    |   Para obtener más información, vea BitLocker – [Removable Drive Configuración](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings#bitlocker---removable-drive-settings.md).      |

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
