---
title: Compatibilidad de soluciones antivirus con Defender para endpoint
description: Obtenga información sobre cómo Windows Defender funciona con Microsoft Defender para Endpoint. Aprenda también cómo funciona Defender for Endpoint cuando se usa un cliente antimalware de terceros.
keywords: Compatibilidad de windows Defender, defender, Microsoft Defender para endpoint, defender para endpoint, antivirus, mde
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: 02c6ecefc5d6393508382c436a9fe82e31200b76
ms.sourcegitcommit: 6c342a956b2dbc32be33bac1a23a5038490f1b40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58533500"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Compatibilidad de soluciones antivirus con Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-defendercompat-abovefoldlink)

El agente de Microsoft Defender para endpoint depende Antivirus de Microsoft Defender para algunas funcionalidades, como el examen de archivos.

> [!IMPORTANT]
> Defender for Endpoint no se adhiere a la configuración Antivirus de Microsoft Defender exclusiones.

Debe configurar las actualizaciones de inteligencia de seguridad en los dispositivos defender para puntos de conexión Antivirus de Microsoft Defender es el antimalware activo o no. Para obtener más información, vea [Manage Antivirus de Microsoft Defender updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).

Si un dispositivo incorporado está protegido por un cliente antimalware de terceros, Antivirus de Microsoft Defender en ese punto de conexión entrarán en modo pasivo.

Antivirus de Microsoft Defender seguirá recibiendo actualizaciones y el *mspeng.exe* se mostrará como un servicio en ejecución. Sin embargo, no realizará exámenes y no reemplazará al cliente antimalware de terceros en ejecución.

La Antivirus de Microsoft Defender se deshabilitará. Los usuarios del dispositivo no podrán usar el Antivirus de Microsoft Defender realizar exámenes a petición o configurar la mayoría de las opciones.

Para obtener más información, vea [el tema Antivirus de Microsoft Defender y defender para la](microsoft-defender-antivirus-compatibility.md)compatibilidad de extremos .
