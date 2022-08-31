---
title: Abordar falsos positivos o falsos negativos en Microsoft 365 Defender
description: ¿Se ha detectado algo extraño o erróneamente por AIR en Microsoft 365 Defender? Obtenga información sobre cómo enviar falsos positivos o falsos negativos a Microsoft para su análisis.
keywords: automated, investigation, alert, remediation, false positive, false negative
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.openlocfilehash: cab16efa7f5118a4b9fce44713536dc043dd6b7b
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482392"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a>Abordar falsos positivos o falsos negativos en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

En ocasiones, se pueden producir falsos positivos o negativos con cualquier solución de protección contra amenazas. Si [las funcionalidades automatizadas de investigación y respuesta](m365d-autoir.md) en Microsoft 365 Defender han perdido o detectado algo erróneamente, hay pasos que el equipo de operaciones de seguridad puede realizar:

- [Notificar un falso positivo o negativo a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [Ajuste las alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (si es necesario)
- [Deshacer las acciones de corrección que se realizaron en los dispositivos](#undo-a-remediation-action-that-was-taken-on-a-device)

En las secciones siguientes se describe cómo realizar estas tareas.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Notificar un falso positivo/negativo a Microsoft para su análisis

|Elemento que se ha perdido o se ha detectado de forma incorrecta |Servicio  |Qué hacer  |
|---------|---------|---------|
|- mensaje de Email <br/>- datos adjuntos Email <br/>- Dirección URL en un mensaje de correo electrónico<br/>- Dirección URL en un archivo de Office      |[Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)        |[Enviar sospechas de correo no deseado, phish, direcciones URL y archivos a Microsoft para su examen](../office-365-security/admin-submission.md)         |
|Archivo o aplicación en un dispositivo    |[Microsoft Defender para punto de conexión](/windows/security/threat-protection)         |[Envío de un archivo a Microsoft para el análisis de malware](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Ajuste de una alerta para evitar que los falsos positivos se repitan

|Escenario |Servicio |Qué hacer |
|--------|--------|--------|
|- Un uso legítimo desencadena una alerta <br/>- Una alerta es inexacta    |[Microsoft Defender for Cloud Apps](/cloud-app-security)<br/> o <br/>[Protección contra amenazas de Azure](/azure/security/fundamentals/threat-detection)         |[Administración de alertas en el portal de Defender for Cloud Apps](/cloud-app-security/managing-alerts)         |
|Un archivo, dirección IP, dirección URL o dominio se trata como malware en un dispositivo, aunque sea seguro|[Microsoft Defender para punto de conexión](/windows/security/threat-protection) |[Creación de un indicador personalizado con una acción "Permitir"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Deshacer una acción de corrección realizada en un dispositivo

Si se ha realizado una acción de corrección en una entidad (como un dispositivo o un mensaje de correo electrónico) y la entidad afectada no es realmente una amenaza, el equipo de operaciones de seguridad puede deshacer la acción de corrección en el [Centro de acciones](m365d-action-center.md).

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a> e inicie sesión. 
2. En el panel de navegación, elija **Centro de actividades**. 
3. En la pestaña **Historial** , seleccione una acción que quiera deshacer. Se abre el panel flotante.
4. En el panel flotante, seleccione **Deshacer**.

> [!TIP]
> Consulte [Deshacer acciones completadas](m365d-autoir-actions.md#undo-completed-actions).

## <a name="see-also"></a>Vea también

- [Ver los detalles y los resultados de una investigación automatizada](m365d-autoir-results.md)
- [Búsqueda proactiva de amenazas con la búsqueda avanzada de Microsoft 365 Defender](advanced-hunting-overview.md)
