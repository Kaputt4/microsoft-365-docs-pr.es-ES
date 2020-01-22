---
title: Cómo informar de falsos positivos o falsos negativos en AIR en la protección contra amenazas de Microsoft
description: ¿Perdió o se detectó un error por aire en la protección contra amenazas de Microsoft? Obtenga información sobre cómo enviar falsos positivos o falsos negativos a Microsoft para su análisis.
keywords: automatizado, investigación, alerta, desencadenador, acción, corrección, falso positivo, falso negativo
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: d62f10cdf9805cdcfae7ba5bd5381ca589d1297c
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260198"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Cómo informar de falsos positivos/negativos en capacidades automatizadas de investigación y respuesta

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

¿Las [capacidades automatizadas de investigación y respuesta](mtp-autoir.md) en Microsoft Threat Protection no se han detectado o no detectan nada correctamente? Puede informar a Microsoft o ajustar sus avisos (si es necesario). Use la tabla siguiente como guía: 


|Item  |Detectado por  |Cómo notificarlo  |
|---------|---------|---------|
|Mensaje de correo electrónico <br/>Datos adjuntos de correo <br/>Dirección URL en un mensaje de correo electrónico o un archivo de Office      |[Protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Enviar un correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft para Office 365 Scanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|Archivo o aplicación en un dispositivo    |[Protección contra amenazas avanzada de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection)         |[Enviar un archivo a Microsoft para el análisis de malware](https://www.microsoft.com/wdsi/filesubmission)         |
|Alerta desencadenada por uso legítimo <br/>Alerta no precisa    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> o <br/>[Detección de amenazas avanzadas de Azure](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Administrar alertas en Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |


## <a name="next-steps"></a>Siguientes pasos

- [Aprobar o rechazar acciones relacionadas con la investigación y la respuesta automatizadas](mtp-autoir-actions.md)
- [Más información sobre el Centro de actividades](mtp-action-center.md)
- [Búsqueda proactiva de amenazas con la búsqueda avanzada en la Protección contra amenazas de Microsoft](advanced-hunting-overview.md)
