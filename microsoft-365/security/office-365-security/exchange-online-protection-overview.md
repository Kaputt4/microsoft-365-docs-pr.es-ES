---
title: Exchange Online Protection (EOP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre Exchange Online Protection (EOP) puede ayudar a proteger su organización de correo electrónico local en entornos independientes e híbridos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ad083e828fbed27cce4b8929c1bee3081c983c17
ms.sourcegitcommit: 76c91e7b0d3172de57988eb4576d2b91c2f9ce18
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2021
ms.locfileid: "52707289"
---
# <a name="exchange-online-protection-overview"></a>Información general de Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) es el servicio de filtrado basado en la nube que protege su organización contra correo no deseado, malware y otras amenazas de correo electrónico. EOP se incluye en todas las Microsoft 365 con Exchange Online buzones de correo.

> [!NOTE]
> EOP también está disponible por sí mismo para proteger los buzones locales y en entornos híbridos para proteger los buzones de correo Exchange locales. Para obtener más información, vea [Standalone Exchange Online Protection](/exchange/standalone-eop/standaonline-eop).

Los pasos para configurar las características de seguridad de EOP y una comparación con la seguridad agregada que obtiene en Microsoft Defender para Office 365, consulte [Protect against threats](protect-against-threats.md). La configuración recomendada para las características de EOP está disponible en Configuración recomendada para EOP y [Microsoft Defender para Office 365 seguridad.](recommended-settings-for-eop-and-office365.md)

El resto de este artículo explica cómo funciona EOP y las características disponibles en EOP.

## <a name="how-eop-works"></a>Cómo funciona EOP

Para comprender el funcionamiento de EOP, es muy útil ver cómo se procesa el correo entrante:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Gráfico del correo electrónico de Internet o los comentarios del cliente que pasan a EOP y a través de la conexión, antimalware, el filtrado de reglas de barras diagonales de flujo de correo y el filtrado de contenido, antes del veredicto de correo no deseado o cuarentena, o la entrega de correo del usuario final.":::

1. Cuando un mensaje entrante entra en EOP, pasa inicialmente a través del filtrado de conexiones, lo que comprueba la reputación del remitente. La mayoría del correo no deseado se detiene en este momento y EOP lo rechaza. Para obtener más información, consulte [Configurar filtrado de la conexión](configure-the-connection-filter-policy.md).

2. A continuación, se inspecciona el mensaje en busca de malware. Si se encuentra malware en el mensaje o en los datos adjuntos, el mensaje se enruta a un almacén de cuarentena de solo administrador. Para obtener más información acerca de la protección contra malware, vea [Protección contra malware en EOP](anti-malware-protection.md).

3. El mensaje continúa a través del filtrado de directivas, donde se evalúa con las reglas de flujo de correo (también conocidas como reglas de transporte) que haya creado. Por ejemplo, una regla puede enviar una notificación a un administrador cuando un mensaje llega de un remitente específico.

   En la organización local con Exchange Enterprise CAL con licencias de servicios, las comprobaciones de prevención de pérdida de datos [(DLP)](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) en EOP también se realizan en este momento.

4. El mensaje pasa a través del filtrado de contenido (antispam y contra la suplantación de identidad) donde los mensajes dañinos se identifican como correo no deseado, correo no deseado de elevada confianza, phishing, phishing de elevada confianza o masivo (directivas contra correo no deseado) o suplantación de identidad (configuración de suplantación de identidad en directivas contra suplantación de identidad). Puede configurar la acción para realizar el mensaje en función del veredicto de filtrado (cuarentena, mover a la carpeta correo no deseado, etc.). Para obtener más información, vea [Configure anti-spam policies](configure-your-spam-filter-policies.md) y [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

Un mensaje que pasa correctamente todas estas capas de protección se entrega a los destinatarios.

Para obtener más información, vea [Order and precedence of email protection](how-policies-and-protections-are-combined.md).

### <a name="eop-datacenters"></a>Centros de datos de EOP

EOP se ejecuta en una red mundial de centros de datos que están diseñados para proporcionar la mejor disponibilidad. Por ejemplo, si un centro de datos no está disponible, los mensajes de correo electrónico se enrutan automáticamente a otro centro de datos sin interrupciones del servicio. Los servidores de cada centro de datos aceptan mensajes en su nombre, lo que proporciona una capa de separación entre su organización e Internet, lo que reduce la carga en los servidores. Gracias a esta red de alta disponibilidad, Microsoft se asegura que el correo llegue a la organización de manera puntual.

EOP realiza el equilibrio de carga entre los centros de datos, pero solo dentro de una región. Si está aprovisionado en una región, todos sus mensajes se procesarán usando el enrutamiento de correo de esa región. La siguiente lista muestra cómo funciona el enrutamiento regional de correo para los centros de datos de EOP:

- En Europa, Oriente Medio y África (EMEA), todos los buzones de Exchange Online están ubicados en centros de datos de EMEA, y todos los mensajes se enrutan a través de EMEA para el filtrado de EOP.
- En Asia-Pacific (APAC), todos los buzones de correo Exchange Online se encuentran en centros de datos de APAC y los mensajes se enruta actualmente a través de centros de datos de APAC para el filtrado de EOP.
- En América, los servicios se distribuyen en las siguientes ubicaciones:
  - Sudamérica: Exchange Online buzones de correo se encuentran en centros de datos en Brasil y Chile. Todos los mensajes se enruta a través de centros de datos locales para el filtrado de EOP. Los mensajes en cuarentena se almacenan en el centro de datos donde se encuentra el espacio empresarial.
  - Canadá: Exchange Online buzones de correo se encuentran en centros de datos en Canadá. Todos los mensajes se enruta a través de centros de datos locales para el filtrado de EOP. Los mensajes en cuarentena se almacenan en el centro de datos donde se encuentra el espacio empresarial.
  - Estados Unidos: Exchange Online buzones de correo se encuentran en centros de datos de Estados Unidos. Todos los mensajes se enruta a través de centros de datos locales para el filtrado de EOP. Los mensajes en cuarentena se almacenan en el centro de datos donde se encuentra el espacio empresarial.
- Para la nube de la comunidad de organismos oficiales (GCC), todos los buzones de Exchange Online están ubicados en centros de datos de Estados Unidos y los mensajes se enrutan a través de centros de datos de Estados Unidos para el filtrado de EOP.

### <a name="eop-features"></a>Características de EOP

En esta sección se proporciona una descripción general de alto nivel de las características principales que están disponibles en EOP.

Para obtener información sobre los requisitos, los límites importantes y la disponibilidad de características en todos los planes de suscripción de EOP, consulte [la Exchange Online Protection del servicio](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

**Notas**:

- EOP usa varias listas de bloqueo de URL que ayudan a detectar vínculos malintencionados conocidos dentro de los mensajes.
- EOP usa una amplia lista de dominios que se sabe que envían correo no deseado.
- EOP usa varios motores antimalware para proteger automáticamente a nuestros clientes en todo momento.
- EOP inspecciona la carga activa en el cuerpo del mensaje y todos los datos adjuntos del mensaje en busca de malware.
- Para obtener los valores recomendados para las directivas de protección, vea [Configuración recomendada para EOP y Microsoft Defender para obtener Office 365 seguridad.](recommended-settings-for-eop-and-office365.md)
- Para obtener instrucciones rápidas para configurar directivas de protección, vea [Protect against threats](protect-against-threats.md).

<br>

****
|Característica|Comentarios|
|---|---|
|**Protection**||
|Antimalware|[Protección contra malware en EOP](anti-malware-protection.md) <p> [Preguntas más frecuentes sobre la protección antimalware](anti-malware-protection-faq-eop.yml) <p> [Configurar directivas antimalware en EOP](configure-anti-malware-policies.md)|
|Correo no deseado entrante|[Protección contra correo no deseado en EOP](anti-spam-protection.md) <p> [Preguntas más frecuentes sobre la protección contra correo electrónico no deseado](anti-spam-protection-faq.yml) <p> [Configuración de directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md)|
|Correo no deseado saliente|[Protección contra correo no deseado saliente en EOP](outbound-spam-controls.md) <p> [Configurar el filtrado de correo no deseado saliente en EOP](configure-the-outbound-spam-policy.md) <p> [Controlar el reenvío automático de correo electrónico externo en Microsoft 365](external-email-forwarding.md)|
|Filtrado de la conexión|[Configurar el filtrado de la conexión](configure-the-connection-filter-policy.md)|
|Anti-phishing|[Directivas contra la suplantación de identidad en Microsoft 365](set-up-anti-phishing-policies.md) <p> [Configuración de directivas contra phishing en EOP](configure-anti-phishing-policies-eop.md)|
|Protección contra la suplantación de identidad|[Suplantación de información de inteligencia en EOP](learn-about-spoof-intelligence.md) <p> [Administrar la lista de permitidos o bloqueados del espacio empresarial](tenant-allow-block-list.md)|
|Purga automática de hora cero (ZAP) para mensajes de malware, correo no deseado y phishing entregados|[ZAP en Exchange Online](zero-hour-auto-purge.md)|
|Directivas de seguridad predefinidas|[Directivas de seguridad predefinidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md) <p> [Analizador de configuración para directivas de protección en EOP y Microsoft Defender para Office 365](configuration-analyzer-for-security-policies.md)|
|Lista de inquilinos permitidos/bloqueados|[Administrar la lista de permitidos o bloqueados del espacio empresarial](tenant-allow-block-list.md)|
|Bloquear listas para remitentes de mensajes|[Crear listas de remitentes bloqueados en EOP](create-block-sender-lists-in-office-365.md)|
|Permitir listas para remitentes de mensajes|[Crear listas de remitentes seguros en EOP](create-safe-sender-lists-in-office-365.md)|
|Directory Based Edge Blocking (DBEB)|[Usar bloqueo perimetral basado en directorios para rechazar mensajes enviados a destinatarios no válidos](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|
|**Cuarentena y envíos**||
|Envío de administrador|[Usar el envío de administrador para enviar correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft](admin-submission.md)|
|Envíos de usuario (buzón personalizado)|[Directiva de envíos de usuarios](user-submission.md)|
|Cuarentena: administradores|[Administración de mensajes en cuarentena y archivos como administrador en EOP](manage-quarantined-messages-and-files.md) <p> [Preguntas más frecuentes sobre mensajes en cuarentena](quarantine-faq.yml) <p> [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md) <p> [Encabezados de mensajes de correo no deseado en Microsoft 365](anti-spam-message-headers.md) <p> Puede analizar los encabezados de mensaje de los mensajes en cuarentena mediante el Analizador de [encabezados de mensaje en](https://mha.azurewebsites.net/).|
|Cuarentena: usuarios finales|[Búsqueda y liberación de mensajes en cuarentena como usuario en EOP](find-and-release-quarantined-messages-as-a-user.md) <p> [Usar notificaciones de correo no deseado de usuario para liberar e informar de mensajes en cuarentena](use-spam-notifications-to-release-and-report-quarantined-messages.md)|
|**Flujo de correo**||
|Reglas de flujo de correo|[Reglas de flujo de correo (reglas de transporte) en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) <p> [Condiciones y excepciones de regla de flujo de correo (predicados) en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions) <p> [Acciones de reglas de flujo de correo en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions) <p> [Administrar reglas de flujo de correo en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) <p> [Procedimientos de regla de flujo de correo Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-procedures)|
|Dominios aceptados|[Administrar dominios aceptados en Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)|
|Conectores|[Configurar el flujo de correo mediante conectores en Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)|
|Filtrado avanzado para conectores|[Filtrado mejorado para conectores en Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)|
|**Supervisión**||
|Seguimiento de mensajes|[Seguimiento de mensajes](message-trace-scc.md) <p> [Seguimiento de mensajes en el Centro Exchange administración](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)|
|Informes de colaboración & correo electrónico|[Ver informes de seguridad de correo electrónico](view-email-security-reports.md)|
|Informes de flujo de correo|[Ver informes de flujo de correo](view-mail-flow-reports.md) <p> [Informes de flujo de correo en el centro Exchange administración](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|Información sobre el flujo de correo|[Información sobre el flujo de correo](mail-flow-insights-v2.md) <p> [Información sobre el flujo de correo en el centro Exchange administración](/exchange/monitoring/mail-flow-insights/mail-flow-insights)|
|Informes de auditoría|[Informes de auditoría en el Centro Exchange administración](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)|
|Directivas de alerta|[Directivas de alerta](../../compliance/alert-policies.md)|
|**Acuerdos de nivel de servicio (SLA) y soporte técnico**||
|SLA de efectividad en cuanto a correo no deseado|\> 99%|
|SLA sobre proporción de falsos positivos|\< 1:250,000|
|SLA sobre detección y bloqueo de virus|100% de virus conocidos|
|SLA sobre el tiempo de actividad mensual|99,999%|
|Soporte técnico por web y teléfono 24 horas al día, siete días a la semana|[Ayuda y compatibilidad con EOP](help-and-support-for-eop.md).|
|**Otras características**||
|Una red mundial georredundante de servidores|EOP se ejecuta en una red mundial de centros de datos que están diseñados para ayudar a proporcionar la mejor disponibilidad. Para obtener más información, vea la sección centros de [datos de EOP](#eop-datacenters) anterior en este artículo.|
|Puesta en cola de los mensajes cuando el servidor local no puede aceptar correo|Los mensajes en aplazamiento permanecen en nuestras colas durante un día. Los reintentos de envío de mensajes se basan en el error que se obtiene del sistema de correo del destinatario. Los mensajes se reintentan cada 5 minutos, como valor promedio. Para obtener más información, vea [Preguntas más frecuentes sobre mensajes devueltos, aplazados y en cola de EOP](eop-queued-deferred-and-bounced-messages-faq.yml).|
|Cifrado de mensajes de Office 365 disponible como complemento|Para obtener más información, vea [Cifrado en Office 365](../../compliance/encryption.md).|
|||
