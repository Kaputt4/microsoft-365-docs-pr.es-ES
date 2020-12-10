---
title: Acciones de corrección tras la investigación automatizada en Microsoft defender para Office 365
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Obtenga información sobre las acciones de corrección tras la investigación automatizada en Microsoft defender para Office 365.
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 75550352170841b1e6a26512c9e857a7c9e3acd3
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616145"
---
# <a name="remediation-actions-following-automated-investigation-in-microsoft-defender-for-office-365"></a>Acciones de corrección tras la investigación automatizada en Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="remediation-actions"></a>Acciones de corrección

La [funcionalidad de investigación y respuesta automatizada](office-365-air.md) (Air) en [Microsoft Defender para Office 365](office-365-atp.md) incluyen ciertas acciones de corrección. Siempre que una investigación automatizada esté en marcha o se haya completado, normalmente verá una o más medidas correctivas que requieren la aprobación de su equipo de operaciones de seguridad para proceder. Estas acciones de corrección pueden incluir lo siguiente:

- Eliminar temporalmente mensajes de correo electrónico o clústeres
- Bloquear URL (tiempo de clic)
- Desactivar el reenvío de correo externo
- Desactivar la delegación

> [!NOTE]
> En Microsoft defender para Office 365, las investigaciones automatizadas no dan como resultado acciones de corrección que se realizan automáticamente. Las acciones de corrección solo se realizan tras la aprobación del equipo de operaciones de seguridad de la organización.

## <a name="threats-and-remediation-actions"></a>Amenazas y acciones de corrección

En la tabla siguiente se resumen las amenazas y las acciones de corrección adecuadas en Microsoft defender para Office 365. En algunos casos, una investigación automatizada no da como resultado una acción de corrección específica. El equipo de operaciones de seguridad puede investigar y tomar las medidas oportunas como se describe en la tabla siguiente.

****

|Categoría|Amenaza/riesgo|Acción (es) de corrección|
|---|---|---|
|Correo electrónico|Malware|Eliminación temporal de correo electrónico/clúster <br> Si hay más de un puñado de mensajes de correo electrónico en un clúster que contienen malware, se considerará que el clúster es malintencionado.|
|Correo electrónico|Dirección URL malintencionada <br> (Una dirección URL malintencionada se detectó mediante [vínculos seguros en Microsoft defender para Office 365](atp-safe-links.md)).|Eliminación temporal de correo electrónico/clúster <p> El correo electrónico que contiene una dirección URL malintencionada se considera malintencionado.|
|Correo electrónico|Suplantación de identidad|Eliminación temporal de correo electrónico/clúster <br> Si más de un puñado de mensajes de correo electrónico en un clúster contienen intentos de suplantación de identidad, el clúster se considera phish.|
|Correo electrónico|Phish zapped <br> (Los mensajes de correo electrónico se entregaron y [zapped](zero-hour-auto-purge.md)).|Eliminación temporal de correo electrónico/clúster <p> Los informes están disponibles para ver mensajes de zapped. [Consulte si Zap movió un mensaje y preguntas más frecuentes](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message).|
|Correo electrónico|Correo electrónico de phish perdido [notificado](enable-the-report-message-add-in.md) por un usuario|[Investigación automatizada desencadenada por el informe del usuario](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|Correo electrónico|Anomalías de volumen <br> (Las cantidades de correo electrónico recientes superan los 7-10 días anteriores para los criterios coincidentes.)|La investigación automatizada no da como resultado una acción pendiente específica. <p> La anomalía del volumen no es una amenaza clara, pero solo es una indicación de los volúmenes de correo electrónico más grandes en los últimos días en comparación con los últimos 7-10 días. Aunque esto puede indicar posibles problemas, se necesita una confirmación en términos de los veredictos malintencionados o una revisión manual de los mensajes de correo electrónico y los clústeres. Consulte [Buscar correo electrónico sospechoso entregado](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered).|
|Correo electrónico|No se encontraron amenazas <br> (El sistema no encontró amenazas basadas en archivos, direcciones URL o análisis de los veredictos del clúster de correo electrónico).|La investigación automatizada no da como resultado una acción pendiente específica. <p> Las amenazas que se encuentran y [zapped](zero-hour-auto-purge.md) después de que se completa una investigación no se reflejan en las conclusiones numéricas de la investigación, pero esas amenazas se pueden ver en el [Explorador de amenazas](threat-explorer.md).|
|User|Un usuario hizo clic en una dirección URL malintencionada <br> (Un usuario se ha desplazado a una página que se ha encontrado más adelante como malintencionada o un usuario ha omitido una [Página de advertencia de vínculos seguros](atp-safe-links.md#warning-pages-from-safe-links) para llegar a una página malintencionada).|La investigación automatizada no da como resultado una acción pendiente específica. <p> Use el explorador de amenazas para [ver datos sobre direcciones URL y haga clic en veredictos](threat-explorer.md#view-data-about-phishing-urls-and-click-verdict). <p> Si su organización está usando [Microsoft defender para el punto de conexión](https://docs.microsoft.com/windows/security/threat-protection/), considere la posibilidad de [investigar al usuario](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) para determinar si su cuenta está comprometida.|
|User|Un usuario está enviando malware/phish|La investigación automatizada no da como resultado una acción pendiente específica. <p> Es posible que el usuario esté notificando malware o phish, o bien alguien puede [suplantar al usuario](anti-spoofing-protection.md) como parte de un ataque. Use el [Explorador de amenazas](threat-explorer.md) para ver y administrar el correo electrónico que contiene [malware](threat-explorer-views.md#email--malware) o [phish](threat-explorer-views.md#email--phish).|
|User|Reenvío de correo <br> (Las reglas de reenvío de buzones de correo se configuran, que se pueden usar para la exfiltración de datos).|Quitar regla de reenvío <p> Usar la [información del flujo de correo](mail-flow-insights-v2.md), incluido el informe de [mensajes reenviados automáticamente](mfi-auto-forwarded-messages-report.md), para ver detalles más específicos sobre el correo electrónico reenviado.|
|User|Reglas de delegación de correo electrónico <br> (La cuenta de un usuario tiene configurada la delegación).|Quitar regla de delegación <p> Si su organización está usando [Microsoft defender para el punto de conexión](https://docs.microsoft.com/windows/security/threat-protection/), considere la posibilidad de [investigar al usuario](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) que está obteniendo el permiso de delegación.|
|User|Exfiltración de datos <br> (Un usuario infringió [las directivas DLP](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)de correo electrónico o de uso compartido de archivos).|La investigación automatizada no da como resultado una acción pendiente específica. <p> [Ver informes de DLP y realizar acciones](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).|
|User|Envío de correo electrónico anómalo <br> (Un usuario ha enviado recientemente más correo electrónico que durante los 7-10 días anteriores).|La investigación automatizada no da como resultado una acción pendiente específica. <p> Enviar una gran cantidad de correo electrónico no es peligroso por sí mismo; es posible que el usuario simplemente haya enviado un correo electrónico a un grupo grande de destinatarios para un evento. Para investigar, use el [flujo de correo](mail-flow-insights-v2.md), incluido el informe de mapa de flujo de [correo](mfi-mail-flow-map-report.md) , para determinar lo que está ocurriendo y emprender acciones.|
|

## <a name="next-steps"></a>Pasos siguientes

- [Ver los detalles y los resultados de una investigación automatizada en Microsoft defender para Office 365](air-view-investigation-results.md)

- [Ver acciones de corrección pendientes o realizadas después de una investigación automatizada en Microsoft defender para Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Artículos relacionados

- [Obtenga información sobre la investigación automatizada en Microsoft defender para el punto de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Obtenga más información acerca de las capacidades adicionales de Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
