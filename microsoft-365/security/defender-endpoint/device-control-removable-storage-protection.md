---
title: Microsoft Defender para punto de conexión Protección de almacenamiento extraíble del control de dispositivos
description: Comprender las "funcionalidades que ayudan a evitar que el usuario o la máquina o ambos usen medios de almacenamiento extraíbles no autorizados
keywords: medios de almacenamiento extraíbles
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
ms.date: 08/01/2022
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 1add6ea29d38e784733b98646458f19c68fa6be1
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67524092"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender para punto de conexión Protección de almacenamiento extraíble del control de dispositivos


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

Para administrar el almacenamiento externo, use el control de acceso de almacenamiento extraíble en lugar de la [instalación del dispositivo](#device-installation).

**detalles de soporte técnico de Windows 10 y Windows 11**:

- Se aplica en el nivel de dispositivo, en el nivel de usuario. o ambos. Permitir solo a personas específicas que realicen acceso de lectura, escritura y ejecución a un almacenamiento extraíble específico en una máquina específica.
- Compatibilidad con MEM OMA-URI y GPO.
- Para dispositivos Windows, consulte [Almacenamiento extraíble Access Control](device-control-removable-storage-access-control.md).

**Plataforma compatible**: Windows 10, Windows 11

**Detalles de soporte técnico de macOS**:

- Aplicado en el nivel de dispositivo: se aplica la misma directiva para cualquier usuario que haya iniciado sesión.
- Para obtener información específica de macOS, consulte [Control de dispositivos para macOS](mac-device-control-overview.md).

**Plataforma compatible:** macOS Catalina 10.15.4+ (con las extensiones del sistema habilitadas)


### <a name="device-installation"></a>Instalación del dispositivo

**Capacidades** : impedir la instalación con o sin exclusión en función de varias propiedades del dispositivo.

**detalles de soporte técnico de Windows 10 y Windows 11**:

- Aplicado en el nivel de dispositivo: se aplica la misma directiva para cualquier usuario que haya iniciado sesión.
- Admite microsoft Endpoint Manager y objetos directiva de grupo.
- Para obtener más información sobre Windows, consulta [Cómo controlar dispositivos USB y otros medios extraíbles mediante Microsoft Defender para punto de conexión](control-usb-devices-using-intune.md).

**Plataforma compatible**: Windows 10, Windows 11

**Detalles de soporte técnico de macOS**:

- Aplicado en el nivel de dispositivo: se aplica la misma directiva para cualquier usuario que haya iniciado sesión.
- Para obtener información específica de macOS, consulte [Control de dispositivos para macOS](mac-device-control-overview.md).

**Plataforma compatible:** macOS Catalina 10.15.4+ (con las extensiones del sistema habilitadas) o posterior

### <a name="endpoint-dlp-removable-storage"></a>Almacenamiento extraíble dlp de punto de conexión

**Funcionalidades:** audite, advierta o impida que un usuario copie un elemento o información en un medio extraíble o un dispositivo USB.

**Descripción** : para obtener más información sobre Windows, consulte [Información sobre la prevención de pérdida de datos de punto de conexión](../../compliance/endpoint-dlp-learn-about.md).

**Plataforma compatible**: Windows 10, Windows 11

### <a name="bitlocker"></a>BitLocker

**Funcionalidades**:

- Bloquee los datos que se van a escribir en unidades extraíbles que no estén protegidas por BitLocker.
- Bloquear el acceso a unidades extraíbles a menos que se cifren en un equipo propiedad de la organización

**Descripción** : para obtener más información sobre Windows, vea [BitLocker : configuración de unidad extraíble](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).

**Plataforma compatible**: Windows 10, Windows 11
