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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 05/06/2021
ms.subservice: mde
ms.openlocfilehash: 2fcab2ab95623b8d2a7d551b697765bc317d2e42
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67679809"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Compatibilidad de soluciones antivirus con Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-defendercompat-abovefoldlink)

El agente de Microsoft Defender para punto de conexión depende del Antivirus de Microsoft Defender para algunas funcionalidades, como el examen de archivos.

> [!IMPORTANT]
> Defender para punto de conexión no cumple la configuración de Exclusiones del Antivirus de Microsoft Defender.

Debe configurar las actualizaciones de inteligencia de seguridad en los dispositivos de Defender para punto de conexión independientemente de si Antivirus de Microsoft Defender es el antimalware activo o no. Para obtener más información, consulte [Administración de actualizaciones del Antivirus de Microsoft Defender y aplicación de líneas base](manage-updates-baselines-microsoft-defender-antivirus.md).

Si un dispositivo incorporado está protegido por un cliente antimalware de terceros, antivirus de Microsoft Defender en ese punto de conexión entrará en modo pasivo.

Antivirus de Microsoft Defender seguirá recibiendo actualizaciones y el proceso *demspeng.exe* se mostrará como un servicio en ejecución. Sin embargo, no realizará exámenes y no reemplazará al cliente antimalware de terceros en ejecución.

La interfaz antivirus de Microsoft Defender se deshabilitará. Los usuarios del dispositivo no podrán usar el Antivirus de Microsoft Defender para realizar exámenes a petición ni configurar la mayoría de las opciones.

Para obtener más información, consulte el [tema Compatibilidad del Antivirus de Microsoft Defender y Defender para punto de conexión](microsoft-defender-antivirus-compatibility.md).
