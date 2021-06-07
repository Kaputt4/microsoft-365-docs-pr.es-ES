---
title: Compatibilidad de soluciones antivirus con Defender para endpoint
description: Obtenga información sobre Windows Defender funciona con Microsoft Defender para Endpoint y cómo funciona cuando se usa un cliente antimalware de terceros.
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
ms.openlocfilehash: f5a0db755f919cb47c4cd284857ddf4e27d16996
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782890"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Compatibilidad de soluciones antivirus con Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

El agente de Microsoft Defender para endpoint depende Antivirus de Microsoft Defender para algunas funcionalidades, como el examen de archivos.

>[!IMPORTANT]
>Defender for Endpoint no se adhiere a la configuración Antivirus de Microsoft Defender exclusiones. 

Debe configurar las actualizaciones de inteligencia de seguridad en los dispositivos defender para puntos de conexión Antivirus de Microsoft Defender es el antimalware activo o no. Para obtener más información, vea [Manage Antivirus de Microsoft Defender updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).

Si un dispositivo incorporado está protegido por un cliente antimalware de terceros, Antivirus de Microsoft Defender en ese punto de conexión entrará en modo pasivo.

Antivirus de Microsoft Defender seguirá recibiendo actualizaciones y el proceso de *mspeng.exe* aparecerá como un servicio en ejecución, pero no realizará exámenes y no reemplazará al cliente antimalware de terceros en ejecución.

La Antivirus de Microsoft Defender se deshabilitará y los usuarios del dispositivo no podrán usar Antivirus de Microsoft Defender realizar exámenes a petición ni configurar la mayoría de las opciones.

Para obtener más información, vea [el tema Antivirus de Microsoft Defender y defender para la](microsoft-defender-antivirus-compatibility.md)compatibilidad de extremos .
