---
title: Acciones de corrección tras la investigación automatizada en Microsoft Defender para Office 365
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
description: Obtenga información sobre las acciones de corrección después de una investigación automatizada en Microsoft Defender para Office 365.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4966ce860c3d27f003a4fd86e158ce80de8252e2
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142638"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Acciones de corrección en Microsoft Defender para Office 365

## <a name="remediation-actions"></a>Acciones de corrección

Las características de protección contra amenazas [de Microsoft Defender para Office 365](office-365-atp.md) incluyen determinadas acciones de corrección. Estas acciones de corrección pueden incluir:

- Eliminar temporalmente mensajes de correo electrónico o clústeres
- Bloquear URL (tiempo de clic)
- Desactivar el reenvío de correo externo
- Desactivar la delegación

En Microsoft Defender para Office 365, las acciones de corrección no se toman automáticamente. En su lugar, las acciones de corrección solo se toman tras la aprobación por parte del equipo de operaciones de seguridad de la organización.

## <a name="threats-and-remediation-actions"></a>Amenazas y acciones de corrección

Microsoft Defender para Office 365 incluye acciones de corrección para abordar diversas amenazas. Las investigaciones automatizadas suelen dar como resultado una o más acciones correctivas para revisar y aprobar. En algunos casos, una investigación automatizada no da como resultado una acción de corrección específica. Para investigar y realizar las acciones adecuadas, use las instrucciones de la tabla siguiente.

|Categoría|Amenaza/riesgo|Acciones de corrección|
|:---|:---|:---|
|Correo electrónico|Malware|Correo electrónico o clúster de eliminación de forma flexible <p> Si varios mensajes de correo electrónico de un clúster contienen malware, el clúster se considera malintencionado.|
|Correo electrónico|URL malintencionada<br/>(Vínculos seguros detectó una dirección URL [malintencionada).](atp-safe-links.md)|Correo electrónico o clúster de eliminación de forma flexible <p>El correo electrónico que contiene una dirección URL malintencionada se considera malintencionado.|
|Correo electrónico|Suplantación de identidad|Correo electrónico o clúster de eliminación de forma flexible <p> Si más de un número de mensajes de correo electrónico en un clúster contiene intentos de suplantación de identidad, todo el clúster se considera un intento de suplantación de identidad.|
|Correo electrónico|Suplantación de identidad (phish) recortada <br>(Los mensajes de correo electrónico se entregaron y, a [continuación, se zapped).)](zero-hour-auto-purge.md)|Correo electrónico o clúster de eliminación de forma flexible <p>Los informes están disponibles para ver los mensajes recortados. [Vea si ZAP movió un mensaje y las preguntas más frecuentes.](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)|
|Correo electrónico|Correo electrónico de [suplantación de identidad perdida notificado](enable-the-report-message-add-in.md) por un usuario|[Investigación automatizada desencadenada por el informe del usuario](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|Correo electrónico|Anomalía de volumen <br> (Las cantidades de correo electrónico recientes superan los 7-10 días anteriores para la coincidencia de criterios).|La investigación automatizada no da como resultado una acción específica pendiente. <p>La anomalía del volumen no es una amenaza clara, sino simplemente una indicación de volúmenes de correo electrónico más grandes en los últimos días en comparación con los últimos 7-10 días. <p>Aunque un gran volumen de correo electrónico puede indicar posibles problemas, se necesita confirmación en términos de veredictos malintencionados o una revisión manual de los mensajes o clústeres de correo electrónico. Consulte [Buscar correo electrónico sospechoso que se entregó.](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)|
|Correo electrónico|No se encontraron amenazas <br> (El sistema no encontró ninguna amenaza basada en archivos, direcciones URL o análisis de los veredictos del clúster de correo electrónico).|La investigación automatizada no da como resultado una acción específica pendiente. <p>Las amenazas encontradas [y recortadas](zero-hour-auto-purge.md) una vez completada una investigación no se reflejan en los resultados numéricos de una investigación, pero estas amenazas se pueden ver en el Explorador [de amenazas.](threat-explorer.md)|
|Usuario|Un usuario hizo clic en una dirección URL malintencionada <br> (Un usuario ha navegado a una página que posteriormente se [](atp-safe-links.md#warning-pages-from-safe-links) ha encontrado malintencionada o un usuario ha omitido una página de advertencia de Vínculos seguros para ir a una página malintencionada).|La investigación automatizada no da como resultado una acción específica pendiente. <p>Use el Explorador de amenazas para ver datos sobre direcciones URL y hacer clic [en veredictos.](threat-explorer.md#view-phishing-url-and-click-verdict-data) <p>Si su organización usa [Microsoft Defender para Endpoint,](https://docs.microsoft.com/windows/security/threat-protection/) [considere](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) la posibilidad de investigar al usuario para determinar si su cuenta está en peligro.|
|Usuario|Un usuario envía malware o phishing|La investigación automatizada no da como resultado una acción específica pendiente. <p> El usuario podría estar informando de malware [](anti-spoofing-protection.md) o phishing, o alguien podría estar suplantando al usuario como parte de un ataque. Use [el Explorador de amenazas](threat-explorer.md) para ver y controlar el correo electrónico que contiene [malware](threat-explorer-views.md#email--malware) o [phishing.](threat-explorer-views.md#email--phish)|
|Usuario|Reenvío de correo <br> (Se configuran reglas de reenvío de buzones, que se pueden usar para la exfiltración de datos).|Quitar regla de reenvío <p> Use [información sobre el flujo de correo,](mail-flow-insights-v2.md)incluido el [informe](mfi-auto-forwarded-messages-report.md)de mensajes de reenvío automático, para ver detalles más específicos sobre el correo electrónico reenviado.|
|Usuario|Reglas de delegación de correo electrónico <br> (La cuenta de un usuario tiene configurada la delegación).|Quitar regla de delegación <p> Si su organización usa [Microsoft Defender para Endpoint,](https://docs.microsoft.com/windows/security/threat-protection/)considere [la posibilidad de](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) investigar al usuario que está obteniendo el permiso de delegación.|
|Usuario|Exfiltración de datos <br> (Un usuario infringió el correo electrónico o las directivas DLP de uso [compartido de archivos).](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|La investigación automatizada no da como resultado una acción específica pendiente. <p> [Ver informes dlp y tomar medidas.](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports)|
|Usuario|Envío de correo electrónico anómalo <br> (Un usuario envió recientemente más correo electrónico que durante los 7-10 días anteriores).|La investigación automatizada no da como resultado una acción específica pendiente. <p> Enviar un gran volumen de correo electrónico no es malintencionado por sí mismo; es posible que el usuario simplemente haya enviado un correo electrónico a un gran grupo de destinatarios para un evento. Para investigar, use información sobre [](mfi-mail-flow-map-report.md) el flujo de correo, incluido [el](mail-flow-insights-v2.md)informe de mapa de flujo de correo para determinar lo que está sucediendo y tomar medidas.|

## <a name="next-steps"></a>Siguientes pasos

- [Ver detalles y resultados de una investigación automatizada en Microsoft Defender para Office 365](air-view-investigation-results.md)
- [Ver las acciones de corrección pendientes o completadas después de una investigación automatizada en Microsoft Defender para Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Artículos relacionados

- [Más información sobre la investigación automatizada en Microsoft Defender para endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Más información sobre las funcionalidades de Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
