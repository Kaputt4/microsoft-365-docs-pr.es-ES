---
title: Acciones de corrección en Microsoft Defender para Office 365
keywords: AIR, autoIR, Microsoft Defender para punto de conexión, automatizado, investigación, respuesta, corrección, amenazas, avanzado, amenaza, protección
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- m365-security
- m365initiative-defender-office365
description: Obtenga información sobre las acciones de corrección después de la investigación automatizada en Microsoft Defender para Office 365.
ms.date: 04/30/2021
ms.custom:
- air
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: e3a50a2f194c6a82a28082acd8b86fe4b4466301
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68630938"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Acciones de corrección en Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="remediation-actions"></a>Acciones de corrección

Las características de protección contra amenazas de [Microsoft Defender para Office 365](defender-for-office-365.md) incluyen ciertas acciones de corrección. Estas acciones de corrección pueden incluir:

- Eliminar temporalmente mensajes de correo electrónico o clústeres
- Bloquear URL (tiempo de clic)
- Desactivar el reenvío de correo externo
- Desactivar la delegación

En Microsoft Defender para Office 365, las acciones de corrección no se realizan automáticamente. En su lugar, las acciones de corrección solo se realizan tras la aprobación del equipo de operaciones de seguridad de la organización.

## <a name="threats-and-remediation-actions"></a>Amenazas y acciones de corrección

Microsoft Defender para Office 365 incluye acciones de corrección para abordar varias amenazas. Las investigaciones automatizadas suelen dar lugar a una o varias acciones de corrección para revisar y aprobar. En algunos casos, una investigación automatizada no da lugar a una acción de corrección específica. Para investigar y realizar las acciones adecuadas, use las instrucciones de la tabla siguiente.

|Categoría|Amenaza/riesgo|Acciones de corrección|
|:---|:---|:---|
|Correo electrónico|Malware|Eliminación temporal de correo electrónico o clúster <p> Si más de un puñado de mensajes de correo electrónico de un clúster contienen malware, el clúster se considera malintencionado.|
|Correo electrónico|Dirección URL malintencionada <br> ( [Vínculos seguros](safe-links.md) detectó una dirección URL malintencionada).|Eliminación temporal de correo electrónico o clúster <br> Dirección URL de bloqueo (comprobación con el tiempo de clic) <p> Email que contiene una dirección URL malintencionada se considera malintencionada.|
|Correo electrónico|Phish|Eliminación temporal de correo electrónico o clúster <p> Si más de un puñado de mensajes de correo electrónico de un clúster contienen intentos de suplantación de identidad (phishing), todo el clúster se considera un intento de suplantación de identidad (phishing).|
|Correo electrónico|Phish zapped <br> (Email mensajes se entregaron y luego [se zapó](zero-hour-auto-purge.md)).|Eliminación temporal de correo electrónico o clúster <p> Los informes están disponibles para ver los mensajes zapped. [Vea si ZAP movió un mensaje y preguntas más frecuentes](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message).|
|Correo electrónico|Correo electrónico de phish perdido [notificado](enable-the-report-message-add-in.md) por un usuario|[Investigación automatizada desencadenada por el informe del usuario](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|Correo electrónico|Anomalía de volumen <br> (Las cantidades recientes de correo electrónico superan los 7-10 días anteriores para los criterios coincidentes).|La investigación automatizada no da lugar a una acción pendiente específica. <p>La anomalía de volumen no es una amenaza clara, pero es simplemente una indicación de volúmenes de correo electrónico más grandes en los últimos días en comparación con los últimos 7-10 días. <p>Aunque un gran volumen de correo electrónico puede indicar posibles problemas, se necesita confirmación en términos de veredictos malintencionados o una revisión manual de mensajes de correo electrónico o clústeres. Consulte [Buscar correo electrónico sospechoso que se ha entregado](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered).|
|Correo electrónico|No se encontraron amenazas <br> (El sistema no encontró ninguna amenaza basada en archivos, direcciones URL o análisis de veredictos de clústeres de correo electrónico).|La investigación automatizada no da lugar a una acción pendiente específica. <p>Las amenazas encontradas y [zapped](zero-hour-auto-purge.md) una vez completada una investigación no se reflejan en los resultados numéricos de una investigación, pero estas amenazas se pueden ver en [el Explorador de amenazas](threat-explorer.md).|
|User|Un usuario ha hecho clic en una dirección URL malintencionada <br> (Un usuario ha navegado a una página que más adelante se ha detectado como malintencionada o un usuario ha omitido una [página de advertencia vínculos seguros](safe-links.md#warning-pages-from-safe-links) para llegar a una página malintencionada).|La investigación automatizada no da lugar a una acción pendiente específica. <p> Bloquear URL (tiempo de clic) <p> Use el Explorador de amenazas para [ver los datos sobre las direcciones URL y haga clic en veredictos](threat-explorer.md#view-phishing-url-and-click-verdict-data). <p> Si su organización usa [Microsoft Defender para punto de conexión](/windows/security/threat-protection/), considere [la posibilidad de investigar al usuario](/microsoft-365/security/defender-endpoint/investigate-user) para determinar si su cuenta está en peligro.|
|User|Un usuario envía malware/phish|La investigación automatizada no da lugar a una acción pendiente específica. <p> El usuario podría estar informando de malware/phish, o alguien podría estar [suplantando al usuario](anti-spoofing-protection.md) como parte de un ataque. Use [el Explorador de amenazas](threat-explorer.md) para ver y controlar el correo electrónico que contiene [malware](threat-explorer-views.md#email--malware) o [phish](threat-explorer-views.md#email--phish).|
|User|Reenvío de correo <br> (Las reglas de reenvío de buzones están configuradas, se podría usar chch para la filtración de datos).|Quitar regla de reenvío <p> Use [la información de flujo de correo](mail-flow-insights-v2.md), incluido el [informe de mensajes autofowarded](mfi-auto-forwarded-messages-report.md), para ver detalles más específicos sobre el correo electrónico reenviado.|
|User|Email reglas de delegación <br> (La cuenta de un usuario tiene delegaciones configuradas).|Eliminación de la regla de delegación <p> Si su organización usa [Microsoft Defender para punto de conexión](/windows/security/threat-protection/), considere [la posibilidad de investigar al usuario](/microsoft-365/security/defender-endpoint/investigate-user) que obtiene el permiso de delegación.|
|User|Filtración de datos <br> (Un usuario ha infringido las [directivas DLP](../../compliance/dlp-learn-about-dlp.md) de uso compartido de archivos o correo electrónico |La investigación automatizada no da lugar a una acción pendiente específica. <p> [Vea los informes DLP y tome medidas](../../compliance/view-the-dlp-reports.md).|
|User|Envío de correo electrónico anómalo <br> (Un usuario envió recientemente más correo electrónico que durante los 7-10 días anteriores).|La investigación automatizada no da lugar a una acción pendiente específica. <p> El envío de un gran volumen de correo electrónico no es malintencionado por sí mismo; es posible que el usuario acaba de enviar correo electrónico a un gran grupo de destinatarios para un evento. Para investigar, use [la información de flujo de correo](mail-flow-insights-v2.md), incluido el [informe de mapa de flujo de correo](mfi-mail-flow-map-report.md) para determinar lo que está sucediendo y tomar medidas.|

## <a name="next-steps"></a>Pasos siguientes

- [Ver detalles y resultados de una investigación automatizada en Microsoft Defender para Office 365](air-view-investigation-results.md)
- [Ver las acciones de corrección pendientes o completadas después de una investigación automatizada en Microsoft Defender para Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Artículos relacionados

- [Obtenga información sobre la investigación automatizada en Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Más información sobre las funcionalidades de Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)
