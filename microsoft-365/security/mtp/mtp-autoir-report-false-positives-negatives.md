---
title: Controlar falsos positivos o falsos negativos en AIR en Microsoft 365 Defender
description: ¿Se ha detectado algo incorrecto o perdido por AIR en Microsoft 365 Defender? Obtenga información sobre cómo enviar falsos positivos o falsos negativos a Microsoft para su análisis.
keywords: automatizado, investigación, alerta, corrección, falso positivo, falso negativo
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: ccfb2c8d9395d3f64b20980b156ed51545967101
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917075"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Controlar falsos positivos/negativos en capacidades automatizadas de investigación y respuesta

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Los falsos positivos/negativos pueden ocurrir ocasionalmente con cualquier solución de protección contra amenazas. Si [las capacidades automatizadas](mtp-autoir.md) de investigación y respuesta en Microsoft 365 Defender no se detectaron o detectaron incorrectamente algo, hay pasos que el equipo de operaciones de seguridad puede seguir:

- [Notificar un falso positivo/negativo a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Ajustar las alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (si es necesario); y 
- [Deshacer acciones de corrección realizadas en dispositivos](#undo-a-remediation-action-that-was-taken-on-a-device). 

En las secciones siguientes se describe cómo realizar estas tareas.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Notificar un falso positivo/negativo a Microsoft para su análisis

|Elemento perdido o detectado incorrectamente |Servicio  |Qué hacer  |
|---------|---------|---------|
|- Mensaje de correo electrónico <br/>- Datos adjuntos de correo electrónico <br/>- DIRECCIÓN URL en un mensaje de correo electrónico<br/>- DIRECCIÓN URL en un archivo de Office      |[Microsoft Defender para Office 365](../office-365-security/office-365-atp.md)        |[Enviar correo no deseado, phishing, direcciones URL y archivos sospechosos a Microsoft para su análisis](../office-365-security/admin-submission.md)         |
|Archivo o aplicación en un dispositivo    |[Microsoft Defender para punto de conexión](/windows/security/threat-protection)         |[Enviar un archivo a Microsoft para análisis de malware](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Ajustar una alerta para evitar que los falsos positivos se repitan

|Escenario |Servicio |Qué hacer |
|--------|--------|--------|
|- Una alerta se desencadena por uso legítimo <br/>- Una alerta es inexacta    |[Microsoft Cloud App Security](/cloud-app-security)<br/> o <br/>[Detección avanzada de amenazas de Azure](/azure/security/fundamentals/threat-detection)         |[Administrar alertas en el portal de Cloud App Security](/cloud-app-security/managing-alerts)         |
|Un archivo, dirección IP, dirección URL o dominio se trata como malware en un dispositivo, aunque sea seguro|[Microsoft Defender para punto de conexión](/windows/security/threat-protection) |[Crear un indicador personalizado con una acción "Permitir"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Deshacer una acción de corrección que se ha realizado en un dispositivo

Si se ha realizado una acción de corrección en una entidad (como un dispositivo o un mensaje de correo electrónico) y la entidad afectada no es realmente una amenaza, el equipo de operaciones de seguridad puede deshacer la acción de corrección en el Centro de acciones [.](mtp-action-center.md)

1. Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión. 
2. En el panel de navegación, elija **Centro de actividades**. 
3. En la **pestaña** Historial, seleccione una acción que desee deshacer. Se abre el panel desplegable.
4. En el panel desplegable, seleccione **Deshacer**.

> [!TIP]
> Vea [Deshacer acciones completadas](mtp-autoir-actions.md#undo-completed-actions).

## <a name="see-also"></a>Vea también

- [Ver los detalles y los resultados de una investigación automatizada](mtp-autoir-results.md)
- [Búsqueda proactiva de amenazas con búsqueda avanzada en Microsoft 365 Defender](advanced-hunting-overview.md)
- [Dirección de falsos positivos/negativos en Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)