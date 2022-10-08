---
title: Compatibilidad de soluciones antivirus con Defender para punto de conexión
description: Obtenga información sobre cómo funciona Windows Defender con Microsoft Defender para punto de conexión. Aprenda también cómo funciona Defender para punto de conexión cuando se usa un cliente antimalware de terceros.
keywords: compatibilidad de Windows Defender, defender, Microsoft Defender para punto de conexión, defender para punto de conexión, antivirus, mde
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.date: 05/06/2021
ms.subservice: mde
ms.openlocfilehash: a315442832c4884c9cc42f888fcff237bda4f4a0
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68210050"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Compatibilidad de soluciones antivirus con Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-defendercompat-abovefoldlink)

El agente de Microsoft Defender para punto de conexión depende de Microsoft Defender Antivirus para algunas funcionalidades, como el examen de archivos.

> [!IMPORTANT]
> Defender para punto de conexión no se ajusta a la configuración de exclusiones de antivirus de Microsoft Defender.

Debe configurar las actualizaciones de inteligencia de seguridad en los dispositivos de Defender para punto de conexión independientemente de si Microsoft Defender Antivirus es el antimalware activo o no. Para obtener más información, consulte [Administración de actualizaciones Microsoft Defender Antivirus y aplicación de líneas base](manage-updates-baselines-microsoft-defender-antivirus.md).

Si un dispositivo incorporado está protegido por un cliente antimalware de terceros, Microsoft Defender Antivirus en ese punto de conexión entrará en modo pasivo.

Microsoft Defender Antivirus seguirá recibiendo actualizaciones y el proceso *demspeng.exe* se mostrará como un servicio en ejecución. Sin embargo, no realizará exámenes y no reemplazará al cliente antimalware de terceros en ejecución.

Se deshabilitará la interfaz Microsoft Defender Antivirus. Los usuarios del dispositivo no podrán usar Microsoft Defender Antivirus para realizar exámenes a petición ni configurar la mayoría de las opciones.

Para obtener más información, vea el [tema Microsoft Defender Antivirus y Compatibilidad de Defender para punto de conexión](microsoft-defender-antivirus-compatibility.md).
