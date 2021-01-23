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
description: Obtenga información sobre las acciones de corrección después de la investigación automatizada en Microsoft Defender para Office 365.
ms.date: 01/21/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 39032cb187b2654b6ae03c048e706afb665a8761
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939314"
---
# <a name="remediation-actions-following-automated-investigation-in-microsoft-defender-for-office-365"></a>Acciones de corrección tras la investigación automatizada en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="remediation-actions"></a>Acciones de corrección

[Las capacidades automatizadas de investigación](office-365-air.md) y respuesta (AIR) en [Microsoft Defender para Office 365](office-365-atp.md) incluyen determinadas acciones de corrección. Siempre que una investigación automatizada esté en marcha o se haya completado, normalmente verá una o más medidas correctivas que requieren la aprobación de su equipo de operaciones de seguridad para proceder. Estas acciones de corrección pueden incluir:

- Eliminar temporalmente mensajes de correo electrónico o clústeres
- Bloquear URL (tiempo de clic)
- Desactivar el reenvío de correo externo
- Desactivar la delegación

> [!NOTE]
> En Microsoft Defender para Office 365, las investigaciones automatizadas no resultan en acciones de corrección que se toman automáticamente. Las acciones de corrección solo se toman tras la aprobación del equipo de operaciones de seguridad de la organización.

## <a name="threats-and-remediation-actions"></a>Amenazas y acciones de corrección

En la tabla de esta sección se resumen las amenazas y las acciones de corrección adecuadas en Microsoft Defender para Office 365. En algunos casos, una investigación automatizada no da como resultado una acción de corrección específica. El equipo de operaciones de seguridad puede investigar y tomar las medidas adecuadas, como se describe en la tabla siguiente.

|Categoría|Amenaza/riesgo|Acciones de corrección|
|:---|:---|:---|
|Correo electrónico|Malware|Correo electrónico o clúster de eliminación de forma flexible <br> Si varios mensajes de correo electrónico de un clúster contienen malware, el clúster se considera malintencionado.|
|Correo electrónico|URL malintencionada <br> (Vínculos seguros de Microsoft Defender para [Office 365](atp-safe-links.md)detectó una dirección URL malintencionada).|Correo electrónico o clúster de eliminación de forma flexible <p> El correo electrónico que contiene una dirección URL malintencionada se considera malintencionado.|
|Correo electrónico|Suplantación de identidad|Correo electrónico o clúster de eliminación de forma flexible <br> Si más de un número de mensajes de correo electrónico en un clúster contiene intentos de suplantación de identidad( phishing), el clúster se considera phishing.|
|Correo electrónico|Suplantación de identidad (phish) recortada <br> (Los mensajes de correo electrónico se entregaron [y se zapped).)](zero-hour-auto-purge.md)|Correo electrónico o clúster de eliminación de forma flexible <p> Los informes están disponibles para ver los mensajes recortados. [Vea si ZAP movió un mensaje y las preguntas más frecuentes.](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)|
|Correo electrónico|Correo electrónico de [suplantación de identidad perdida notificado](enable-the-report-message-add-in.md) por un usuario|[Investigación automatizada desencadenada por el informe del usuario](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|Correo electrónico|Anomalía de volumen <br> (Las cantidades de correo electrónico recientes superan los 7-10 días anteriores para la coincidencia de criterios).|La investigación automatizada no da como resultado una acción específica pendiente. <p> La anomalía del volumen no es una amenaza clara, sino simplemente una indicación de volúmenes de correo electrónico más grandes en los últimos días en comparación con los últimos 7-10 días. Aunque la anomalía del volumen puede indicar posibles problemas, se necesita confirmación en términos de veredictos malintencionados o una revisión manual de los mensajes de correo electrónico o clústeres. Consulte [Buscar correo electrónico sospechoso que se entregó.](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)|
|Correo electrónico|No se encontraron amenazas <br> (El sistema no encontró ninguna amenaza basada en archivos, direcciones URL o análisis de los veredictos del clúster de correo electrónico).|La investigación automatizada no da como resultado una acción específica pendiente. <p> Las amenazas encontradas [y recortadas](zero-hour-auto-purge.md) una vez completada una investigación no se reflejan en los resultados numéricos de una investigación, pero estas amenazas se pueden ver en el Explorador [de amenazas.](threat-explorer.md)|
|User|Un usuario hizo clic en una dirección URL malintencionada <br> (Un usuario ha navegado a una página que posteriormente se [](atp-safe-links.md#warning-pages-from-safe-links) ha encontrado malintencionada o un usuario ha omitido una página de advertencia de Vínculos seguros para acceder a una página malintencionada).|La investigación automatizada no da como resultado una acción específica pendiente. <p> Use el Explorador de amenazas para ver datos sobre direcciones URL y hacer clic [en veredictos.](threat-explorer.md#view-phishing-url-and-click-verdict-data) <p> Si su organización usa [Microsoft Defender para Endpoint,](https://docs.microsoft.com/windows/security/threat-protection/) [considere](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) la posibilidad de investigar al usuario para determinar si su cuenta está en peligro.|
|User|Un usuario envía malware o phishing|La investigación automatizada no da como resultado una acción específica pendiente. <p> El usuario podría estar informando de malware [](anti-spoofing-protection.md) o phishing, o alguien podría estar suplantando al usuario como parte de un ataque. Use [el Explorador de amenazas](threat-explorer.md) para ver y controlar el correo electrónico que contiene [malware](threat-explorer-views.md#email--malware) o [phishing.](threat-explorer-views.md#email--phish)|
|User|Reenvío de correo <br> (Se configuran reglas de reenvío de buzones, que se pueden usar para la exfiltración de datos).|Quitar regla de reenvío <p> Use [información sobre el flujo de correo,](mail-flow-insights-v2.md)incluido el [informe](mfi-auto-forwarded-messages-report.md)de mensajes de reenvío automático, para ver detalles más específicos sobre el correo electrónico reenviado.|
|User|Reglas de delegación de correo electrónico <br> (La cuenta de un usuario tiene configurada la delegación).|Quitar regla de delegación <p> Si su organización usa [Microsoft Defender para Endpoint,](https://docs.microsoft.com/windows/security/threat-protection/)considere [la posibilidad de investigar](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) al usuario que tiene el permiso de delegación.|
|User|Exfiltración de datos <br> (Un usuario infringió el correo electrónico o las directivas DLP de uso [compartido de archivos).](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|La investigación automatizada no da como resultado una acción específica pendiente. <p> [Ver informes dlp y tomar medidas.](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports)|
|User|Envío de correo electrónico anómalo <br> (Un usuario envió recientemente más correo electrónico que durante los 7-10 días anteriores).|La investigación automatizada no da como resultado una acción específica pendiente. <p> Enviar un gran volumen de correo electrónico no es malintencionado por sí mismo; es posible que el usuario simplemente haya enviado un correo electrónico a un gran grupo de destinatarios para un evento. Para investigar, use información sobre [](mfi-mail-flow-map-report.md) el flujo de correo, incluido [el](mail-flow-insights-v2.md)informe de mapa de flujo de correo para determinar lo que está sucediendo y tomar medidas.|
|

## <a name="next-steps"></a>Siguientes pasos

- [Ver detalles y resultados de una investigación automatizada en Microsoft Defender para Office 365](air-view-investigation-results.md)

- [Ver las acciones de corrección pendientes o completadas después de una investigación automatizada en Microsoft Defender para Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Artículos relacionados

- [Más información sobre la investigación automatizada en Microsoft Defender para endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Más información sobre las funcionalidades de Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
