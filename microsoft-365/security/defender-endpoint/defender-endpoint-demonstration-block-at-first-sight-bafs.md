---
title: demostración de Microsoft Defender para punto de conexión Bloquear a primera vista (BAFS)
description: Una demostración que muestra cómo Block at First Sight detecta y bloquea el nuevo malware en cuestión de segundos.
keywords: Microsoft Defender para punto de conexión, protección proporcionada en la nube, detección de malware, bloqueo de malware, demostración
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: evaluation
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 2b6b45ed57d0b7c76263021ae57b706bb476ce18
ms.sourcegitcommit: 55672e44de74209f2e23b4bd9ca74a2ee7e88cd9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2022
ms.locfileid: "68319563"
---
# <a name="block-at-first-sight-bafs-demonstration"></a>Demostración de bloquear a primera vista (BAFS)

Bloquear a primera vista es una característica de Microsoft Defender protección proporcionada por la nube antivirus que proporciona una manera de detectar y bloquear nuevo malware en cuestión de segundos. Puede probar que funciona según lo esperado descargando un archivo de malware falso.

## <a name="scenario-requirements-and-setup"></a>Requisitos y configuración del escenario

- Windows 10 actualización de aniversario (1607) o posterior
- Protección en la nube habilitada
- Puede [descargar y usar el script de PowerShell](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings/) para habilitar esta configuración y otras
- Nota: Debería ver que el explorador le pide que guarde este archivo en unos segundos.

### <a name="test-bafs"></a>Prueba de BAFS

- Haga clic en el botón Crear y descargar nuevo archivo.
- Debería ver el explorador que examina el archivo, seguido de una notificación de bloque antivirus.
- [Crear & descargar nuevo archivo!](https://demowdtestground.blob.core.windows.net/samples/ztp_xzXLX_s1H8MsxK2SRlsjmzaH62cOZEaqtstGsOw/wdtestfile.exe?sv=2015-07-08&sr=b&sig=7JNcGzAYWEinuWKNmjoC6tDmEjGZMQj8rAEF9HIzJdE%3D&se=2022-09-30T18%3A29%3A28Z&sp=r)

## <a name="see-also"></a>Vea también

[Bloquear a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md)

[Microsoft Defender para punto de conexión: escenarios de demostración](defender-endpoint-demonstrations.md)
