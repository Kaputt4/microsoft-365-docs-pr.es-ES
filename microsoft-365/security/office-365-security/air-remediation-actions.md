---
title: Acciones de corrección en Microsoft Defender para Office 365
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automated, investigation, response, remediation, threats, advanced, threat, protection
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Obtenga información sobre las acciones de corrección después de la investigación automatizada en Microsoft Defender para Office 365.
ms.date: 04/30/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71c8ca842d9c88086dee041316899bbc08f943fe
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185585"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Acciones de corrección en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="remediation-actions"></a>Acciones de corrección

Las características de protección contra amenazas [en Microsoft Defender para Office 365](defender-for-office-365.md) incluyen determinadas acciones de corrección. Estas acciones de corrección pueden incluir:

- Eliminar temporalmente mensajes de correo electrónico o clústeres
- Bloquear URL (tiempo de clic)
- Desactivar el reenvío de correo externo
- Desactivar la delegación

En Microsoft Defender para Office 365, las acciones de corrección no se toman automáticamente. En su lugar, las acciones de corrección solo se toman tras la aprobación del equipo de operaciones de seguridad de la organización.

## <a name="threats-and-remediation-actions"></a>Amenazas y acciones de corrección

Microsoft Defender para Office 365 incluye acciones de corrección para abordar diversas amenazas. Las investigaciones automatizadas suelen dar como resultado una o más acciones de corrección para revisar y aprobar. En algunos casos, una investigación automatizada no da como resultado una acción de corrección específica. Para investigar y realizar las acciones apropiadas, use las instrucciones de la tabla siguiente.

|Categoría|Amenaza/riesgo|Acciones de corrección|
|:---|:---|:---|
|Correo electrónico|Malware|Correo electrónico o clúster de eliminación suave <p> Si más de un puñado de mensajes de correo electrónico en un clúster contienen malware, se considera que el clúster es malintencionado.|
|Correo electrónico|URL malintencionada <br> (Se detectó una dirección URL malintencionada [Caja fuerte links](safe-links.md).)|Correo electrónico o clúster de eliminación suave <br> Dirección URL de bloqueo (comprobación del tiempo de clic) <p> El correo electrónico que contiene una dirección URL malintencionada se considera malintencionado.|
|Correo electrónico|Suplantación de identidad|Correo electrónico o clúster de eliminación suave <p> Si más de un puñado de mensajes de correo electrónico en un clúster contienen intentos de phishing, todo el clúster se considera un intento de suplantación de identidad.|
|Correo electrónico|Phish de zapped <br> (Los mensajes de correo electrónico se entregaron y luego [se zapped](zero-hour-auto-purge.md).)|Correo electrónico o clúster de eliminación suave <p> Los informes están disponibles para ver los mensajes recortados. [Vea si ZAP movió un mensaje y preguntas frecuentes](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message).|
|Correo electrónico|Correo electrónico de [suplantación de identidad omitida notificado](enable-the-report-message-add-in.md) por un usuario|[Investigación automatizada desencadenada por el informe del usuario](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|Correo electrónico|Anomalía de volumen <br> (Las cantidades de correo electrónico recientes superan los 7-10 días anteriores para los criterios de coincidencia).|La investigación automatizada no da como resultado una acción pendiente específica. <p>La anomalía del volumen no es una amenaza clara, sino simplemente una indicación de volúmenes de correo electrónico más grandes en los últimos días en comparación con los últimos 7-10 días. <p>Aunque un gran volumen de correo electrónico puede indicar posibles problemas, la confirmación es necesaria en términos de veredictos malintencionados o una revisión manual de mensajes de correo electrónico o clústeres. Consulte [Buscar correo electrónico sospechoso que se entregó](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered).|
|Correo electrónico|No se encontraron amenazas <br> (El sistema no encontró ninguna amenaza basada en archivos, direcciones URL o análisis de los veredictos del clúster de correo electrónico).|La investigación automatizada no da como resultado una acción pendiente específica. <p>Las amenazas encontradas [y zapped](zero-hour-auto-purge.md) una vez completada una investigación no se reflejan en los resultados numéricos de una investigación, pero estas amenazas se pueden ver en el Explorador [de amenazas](threat-explorer.md).|
|Usuario|Un usuario hizo clic en una dirección URL malintencionada <br> (Un usuario ha navegado a una página que más tarde se encontró que era malintencionada o un usuario omitió una página de advertencia de [vínculos](safe-links.md#warning-pages-from-safe-links) de Caja fuerte para llegar a una página malintencionada).|La investigación automatizada no da como resultado una acción pendiente específica. <p> Bloquear URL (tiempo de clic) <p> Use el Explorador de amenazas [para ver datos sobre direcciones URL y hacer clic en veredictos.](threat-explorer.md#view-phishing-url-and-click-verdict-data) <p> Si su organización usa [Microsoft Defender para endpoint,](/windows/security/threat-protection/)considere la posibilidad [de investigar al usuario](/microsoft-365/security/defender-endpoint/investigate-user) para determinar si su cuenta está en peligro.|
|Usuario|Un usuario envía malware/phish|La investigación automatizada no da como resultado una acción pendiente específica. <p> El usuario puede estar informando de malware/phish, o alguien podría estar suplantando al usuario [como](anti-spoofing-protection.md) parte de un ataque. Use [el Explorador de](threat-explorer.md) amenazas para ver y controlar el correo electrónico que contiene [malware](threat-explorer-views.md#email--malware) o [phish](threat-explorer-views.md#email--phish).|
|Usuario|Reenvío de correo <br> (Las reglas de reenvío de buzones están configuradas, chch podría usarse para la exfiltración de datos).|Quitar regla de reenvío <p> Use [la información sobre el flujo de correo,](mail-flow-insights-v2.md)incluido el [informe](mfi-auto-forwarded-messages-report.md)de mensajes enviados automáticamente, para ver detalles más específicos sobre el correo electrónico reenviado.|
|Usuario|Reglas de delegación de correo electrónico <br> (La cuenta de un usuario tiene las delegaciones configuradas).|Quitar regla de delegación <p> Si su organización usa [Microsoft Defender para endpoint,](/windows/security/threat-protection/)considere [la posibilidad de investigar al usuario](/microsoft-365/security/defender-endpoint/investigate-user) que está obteniendo el permiso de delegación.|
|Usuario|Filtración de datos <br> (Un usuario infringió las directivas DLP de correo electrónico o de uso [compartido de archivos](../../compliance/dlp-learn-about-dlp.md) |La investigación automatizada no da como resultado una acción pendiente específica. <p> [Ver informes dlp y tomar medidas.](../../compliance/view-the-dlp-reports.md)|
|Usuario|Envío de correo electrónico anómalo <br> (Un usuario envió recientemente más correo electrónico que durante los 7-10 días anteriores).|La investigación automatizada no da como resultado una acción pendiente específica. <p> Enviar un gran volumen de correo electrónico no es malintencionado por sí solo; es posible que el usuario acaba de enviar correo electrónico a un gran grupo de destinatarios para un evento. Para investigar, use información sobre [](mfi-mail-flow-map-report.md) el flujo [de](mail-flow-insights-v2.md)correo, incluido el informe de mapa de flujo de correo para determinar lo que está sucediendo y tomar medidas.|

## <a name="next-steps"></a>Pasos siguientes

- [Ver detalles y resultados de una investigación automatizada en Microsoft Defender para Office 365](air-view-investigation-results.md)
- [Ver acciones de corrección pendientes o completadas después de una investigación automatizada en Microsoft Defender para Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Artículos relacionados

- [Obtenga información sobre la investigación automatizada en Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Obtenga información sobre las funcionalidades en Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)
