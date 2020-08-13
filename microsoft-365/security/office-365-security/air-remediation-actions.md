---
title: Acciones de corrección en Microsoft 365 de investigación y respuesta automatizada
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
ms.collection: M365-security-compliance
description: Obtenga información sobre las acciones de corrección en la investigación automatizada y las capacidades de respuesta en Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 761ae38250dc084a248203dd78b66ed18ea9c401
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653382"
---
# <a name="remediation-actions-in-microsoft-365"></a>Acciones de corrección en Microsoft 365

## <a name="remediation-actions"></a>Acciones de corrección

La [funcionalidad de investigación y respuesta automatizada](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (Air) en [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 incluyen determinadas acciones de corrección. Siempre que se ejecuta una investigación automatizada o se ha completado, normalmente verá una o más acciones de corrección que requieren la aprobación del equipo de operaciones de seguridad para continuar. Estas acciones de corrección pueden incluir lo siguiente:

- Eliminar temporalmente mensajes de correo electrónico o clústeres
- Bloquear URL (tiempo de clic)
- Desactivar el reenvío de correo externo
- Desactivar la delegación

> [!NOTE]
> En Office 365 ATP, las investigaciones automatizadas no se corrigen automáticamente. Solo se realizan acciones de corrección tras obtener la aprobación del equipo de seguridad de su organización.

## <a name="threats-and-remediation-actions"></a>Amenazas y acciones de corrección

En la tabla siguiente se resumen las amenazas y las acciones de corrección adecuadas en Office 365 ATP. En algunos casos, una investigación automatizada no da como resultado una acción de corrección específica. El equipo de operaciones de seguridad puede investigar y tomar las medidas oportunas como se describe en la tabla siguiente.

****

|Categoría|Amenaza/riesgo|Acción (es) de corrección|
|---|---|---|
|Correo electrónico|Malware|Eliminación temporal de correo electrónico/clúster <br/><br/>Si hay más de un puñado de mensajes de correo electrónico en un clúster que contienen malware, se considerará que el clúster es malintencionado.|
|Correo electrónico|Dirección URL malintencionada<br/>(Una dirección URL malintencionada se detectó mediante [vínculos seguros de Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/how-atp-safe-links-works)).|Eliminación temporal de correo electrónico/clúster <br/><br/>El correo electrónico que contiene una dirección URL malintencionada se considera malintencionado.|
|Correo electrónico|Suplantación de identidad|Eliminación temporal de correo electrónico/clúster <br/><br/>Si más de un puñado de mensajes de correo electrónico en un clúster contienen intentos de suplantación de identidad, el clúster se considera phish.|
|Correo electrónico|Phish zapped <br/>(Los mensajes de correo electrónico se entregaron y [zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge)).|Eliminación temporal de correo electrónico/clúster <br/><br/>Los informes están disponibles para ver mensajes de zapped. [Consulte si Zap movió un mensaje y preguntas más frecuentes](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge#how-to-see-if-zap-moved-your-message).|
|Correo electrónico|Correo electrónico de phish perdido [notificado](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) por un usuario|[Investigación automatizada desencadenada por el informe del usuario](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|Correo electrónico|Anomalías de volumen <br/>(Las cantidades de correo electrónico recientes superan los 7-10 días anteriores para los criterios coincidentes.)|La investigación automatizada no da como resultado una acción pendiente específica. <br/><br/>La anomalía del volumen no es una amenaza clara, pero solo es una indicación de los volúmenes de correo electrónico más grandes en los últimos días en comparación con los últimos 7-10 días. Aunque esto puede indicar posibles problemas, se necesita una confirmación en términos de los veredictos malintencionados o una revisión manual de los mensajes de correo electrónico y los clústeres. Consulte [Buscar y eliminar correo electrónico sospechoso que se entregó](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered#find-and-delete-suspicious-email-that-was-delivered).|
|Correo electrónico|No se encontraron amenazas <br/>(El sistema no encontró amenazas basadas en archivos, direcciones URL o análisis de los veredictos del clúster de correo electrónico).|La investigación automatizada no da como resultado una acción pendiente específica. <br/><br/>Las amenazas que se encuentran y [zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge) después de que se completa una investigación no se reflejan en las conclusiones numéricas de la investigación, pero esas amenazas se pueden ver en el [Explorador de amenazas](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer).|
|Usuario|Un usuario hizo clic en una dirección URL malintencionada <br/>(Un usuario se ha desplazado a una página que se ha encontrado más adelante como malintencionada o un usuario ha omitido una [Página de advertencia de vínculos seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-warning-pages) para llegar a una página malintencionada).|La investigación automatizada no da como resultado una acción pendiente específica. <br/><br/>Use el explorador de amenazas para [ver datos sobre direcciones URL y haga clic en veredictos](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer#view-data-about-phishing-urls-and-click-verdict). <br/><br/>Si su organización usa la [protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/), considere la posibilidad de [investigar al usuario](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) para determinar si su cuenta está comprometida.|
|Usuario|Un usuario está enviando malware/phish|La investigación automatizada no da como resultado una acción pendiente específica. <br/><br/>Es posible que el usuario esté notificando malware o phish, o bien alguien puede [suplantar al usuario](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection) como parte de un ataque. Use el [Explorador de amenazas](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) para ver y administrar el correo electrónico que contiene [malware](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--malware) o [phish](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--phish).|
|Usuario|Reenvío de correo <br/>(Las reglas de reenvío de buzones de correo se configuran, que se pueden usar para la exfiltración de datos).|Quitar regla de reenvío <br/><br/>Usar la [información del flujo de correo](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2), incluido el informe de [mensajes reenviados automáticamente](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report), para ver detalles más específicos sobre el correo electrónico reenviado.|
|Usuario|Reglas de delegación de correo electrónico <br/>(La cuenta de un usuario tiene configurada la delegación).|Quitar regla de delegación <br/><br/> Si su organización usa la [protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/), considere la posibilidad de [investigar al usuario](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) que obtiene el permiso de delegación.|
|Usuario|Exfiltración de datos<br/>(Un usuario infringió [las directivas DLP](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)de correo electrónico o de uso compartido de archivos).|La investigación automatizada no da como resultado una acción pendiente específica. <br/><br/>[Ver informes de DLP y realizar acciones](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).|
|Usuario|Envío de correo electrónico anómalo <br/>(Un usuario ha enviado recientemente más correo electrónico que durante los 7-10 días anteriores).|La investigación automatizada no da como resultado una acción pendiente específica. <br/><br/>Enviar una gran cantidad de correo electrónico no es peligroso por sí mismo; es posible que el usuario simplemente haya enviado un correo electrónico a un grupo grande de destinatarios para un evento. Para investigar, use el [flujo de correo](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2), incluido el informe de mapa de flujo de [correo](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-mail-flow-map-report) , para determinar lo que está ocurriendo y emprender acciones.|
|

## <a name="next-steps"></a>Pasos siguientes

- [Ver los detalles y los resultados de una investigación automatizada en Microsoft 365](air-view-investigation-results.md)

- [Ver acciones de corrección pendientes o realizadas tras una investigación automatizada en Microsoft 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Artículos relacionados

- [Investigación automatizada en protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Obtener información sobre la protección contra amenazas de Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)