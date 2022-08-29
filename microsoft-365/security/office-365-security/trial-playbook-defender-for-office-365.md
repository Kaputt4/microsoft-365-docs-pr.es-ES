---
title: Versión de prueba del cuaderno de estrategias de Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.collection: m365-security-compliance
ms.localizationpriority: high
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: m365-security
search.appverid:
- MOE150
- MET150
description: Soluciones para la versión de prueba del cuaderno de estrategias de Microsoft Defender para Office 365
ms.technology: mdo
ms.custom: trial-playbook
ms.openlocfilehash: 942752a8fc13a9644558f20567d7dd32e991867b
ms.sourcegitcommit: 7374c7b013890744d74e5214f7f8d69ca7874466
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "67408073"
---
# <a name="trial-playbook-microsoft-defender-for-office-365"></a>Versión de prueba del cuaderno de estrategias: Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a:**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Bienvenido a la versión de prueba del cuaderno de estrategias de Microsoft Defender para Office 365. Este cuaderno de estrategias te ayudará a sacarle el máximo partido a tu prueba gratuita de 90 días al enseñarte cómo proteger tu organización con Defender para Office 365.

Ahora tiene la opción de probar Defender para Office 365 de una de estas dos maneras:

- **Modo de bloqueo (recomendado)**: si el registro del intercambio de correo (MX) apunta a Microsoft 365, puede evaluar las funcionalidades de Defender para Office 365 en modo de bloqueo. Defender para Office 365 aplica automáticamente la configuración de la[directiva de seguridad estándar preestablecida](preset-security-policies.md).

  A lo largo del período de evaluación, puede elegir en cualquier momento optar por una plantilla de protección superior (nuestra configuración de directiva de seguridad preestablecida estricta) o crear sus propias directivas de protección individuales para que se adapten a sus necesidades.

- **Modo de Auditoría**: si el registro MX apunta a otro lugar distinto de Microsoft 365 (por ejemplo, una puerta de enlace de correo electrónico de terceros), puede evaluar Defender para Office 365 en modo auditoría. Defender para Office 365 no realizará ninguna acción de bloqueo en los mensajes que determinemos que son perjudiciales.

  Estas amenazas se registrarán y estarán disponibles para su revisión a través del [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report), que proporciona información detallada sobre los tipos de amenazas detectadas, a quién se dirigen las amenazas y mucho más. Estas "capturas" adicionales indican las capacidades de protección adicionales de Defender para Office 365 sobre las capacidades estándar de Exchange Online Protection (EOP) o las capacidades de otras puertas de enlace de correo electrónico de terceros. Una vez que esté satisfecho y listo para usar Defender para Office 365, puede [migrar a Defender para Office 365](migrate-to-defender-for-office-365.md).

:::image type="content" source="../../media/mdo-trial-playbook-what-is-mdo.png" alt-text="Representación gráfica de todos los componentes de Microsoft Defender para Office 365" lightbox="../../media/mdo-trial-playbook-what-is-mdo.png":::

Con las recomendaciones de esta guía, aprenderá cómo Defender para Office 365 puede ayudarle a definir directivas de protección, analizar amenazas para su organización y responder a ataques.

Comencemos

## <a name="blocking-mode"></a>Modo de bloqueo

### <a name="step-1-getting-started-in-blocking-mode"></a>Paso 1: Introducción al modo de bloqueo

#### <a name="start-your-microsoft-defender-for-office-365-trial"></a>Iniciar la versión de prueba de Microsoft Defender para Office 365

Después de iniciar la versión de prueba y completar el [proceso de configuración](try-microsoft-defender-for-office-365.md#set-up-an-evaluation-in-blocking-mode), los cambios pueden tardar hasta 2 horas en surtir efecto.

Hemos configurado automáticamente las directivas de [Seguridad preestablecidas](preset-security-policies.md) en su entorno. Estas directivas representan un perfil de protección de línea base adecuado para la mayoría de los usuarios. La protección estándar incluye:

- Vínculos seguros, datos adjuntos seguros y directivas contra la suplantación de identidad que engloban todo el espacio empresarial o el subconjunto de usuarios que hayas elegido durante el proceso de configuración de prueba.
- Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams.
- Protección de vínculos seguros para aplicaciones de Office 365 compatibles.

Mira este vídeo para obtener más información: [Protección contra vínculos malintencionados con Vínculos seguros en Microsoft Defender para Office 365 - YouTube](https://www.youtube.com/watch?v=vhIJ1Veq36Y&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=9).

#### <a name="enable-users-to-report-suspicious-content-in-blocking-mode"></a>Permitir que los usuarios notifiquen contenido sospechoso en modo de bloqueo

Defender para Office 365 permite a los usuarios notificar mensajes a sus equipos de seguridad y permite que los administradores envíen mensajes a Microsoft para ser analizados.

- Implementa [el complemento Mensaje de informe o el complemento Notificar suplantación de identidad (phishing)](enable-the-report-message-add-in.md).
- Establece un flujo de trabajo para [Notificar falsos positivos y falsos negativos](report-false-positives-and-false-negatives.md).
- Usa el [Portal de envíos](admin-submission.md).

Mira este vídeo para obtener más información: [Aprender a usar el portal de envíos para enviar mensajes para ser analizados - YouTube](https://www.youtube.com/watch?v=ta5S09Yz6Ks&ab_channel=MicrosoftSecurit).

#### <a name="review-reports-to-understand-the-threat-landscape-in-blocking-mode"></a>Revisar informes para comprender el panorama de amenazas en modo de bloqueo

Usa las funcionalidades de informe de Defender para Office 365 para obtener más detalles sobre tu entorno.

- Comprende las amenazas recibidas en las herramientas de correo electrónico y de colaboración con el [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).
- Consulta dónde se bloquean las amenazas con el [informe de estado del Flujo de correo](view-email-security-reports.md#mailflow-status-report).
- [Revisa los vínculos](view-reports-for-mdo.md#url-protection-report) que han visto los usuarios o que el sistema ha bloqueado.

:::image type="content" source="../../media/mdo-trial-playbook-reporting.png" alt-text="Correos electrónicos e informes de colaboración en el portal de Microsoft 365 Defender" lightbox="../../media/mdo-trial-playbook-reporting.png":::

### <a name="step-2-intermediate-steps-in-blocking-mode"></a>Paso 2: Pasos intermedios en modo de bloqueo

#### <a name="prioritize-focus-on-your-most-targeted-users"></a>Prioriza el enfoque en los principales usuarios de destino

Protege a los principales usuarios de destino y a los usuarios más visibles con Priority Account Protection en Defender para Office 365, lo que ayuda a priorizar el flujo de trabajo para garantizar la seguridad estos usuarios.

- Identifica los principales usuarios de destino o los usuarios visibles.
- [Etiqueta a estos usuarios](../../admin/setup/priority-accounts.md#add-priority-accounts-from-the-setup-page) como cuentas de prioridad.
- Realiza un seguimiento de las amenazas a la cuenta de prioridad en todo el portal.

Mira este vídeo para obtener más información: [Proteger las cuentas de prioridad en Microsoft Defender para Office 365 - YouTube](https://www.youtube.com/watch?v=tqnj0TlzQcI&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=11).

:::image type="content" source="../../media/mdo-trial-playbook-alerts.png" alt-text="Alertas en el portal de Microsoft 365 Defender." lightbox="../../media/mdo-trial-playbook-alerts.png":::

### <a name="avoid-costly-breaches-by-preventing-user-compromise"></a>Evita infracciones costosas al impedir que el usuario se vea en peligro

Recibe alertas sobre posibles peligros y limita automáticamente el impacto de estas amenazas para evitar que los atacantes obtengan un acceso más profundo a tu entorno.

- Revisa las [alertas de usuarios en peligro](address-compromised-users-quickly.md#compromised-user-alerts).
- [Investigar y responder](address-compromised-users-quickly.md) a usuarios en peligro.

:::image type="content" source="../../media/mdo-trial-playbook-investigation.png" alt-text="Investigación de usuarios en peligro." lightbox="../../media/mdo-trial-playbook-investigation.png":::

Mira este vídeo para obtener más información: [Detectar y responder a un peligro en Microsoft Defender para Office 365 - YouTube](https://www.youtube.com/watch?v=Pc7y3a-wdR0&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=5).

#### <a name="use-threat-explorer-to-investigate-malicious-email"></a>Usa el Explorador de amenazas para investigar el correo electrónico malintencionado

Defender para Office 365 permite investigar las actividades que ponen en peligro a las personas de la organización y tomar medidas para proteger la organización. Puedes hacerlo con el [Explorador de amenazas o (detecciones en tiempo real)](threat-explorer.md)

- [Buscar correo electrónico sospechoso que haya sido entregado](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered): buscar y eliminar mensajes, identificar la dirección IP de un remitente de correo electrónico malintencionado o abrir un incidente para una investigación posterior.
- [Comprobar la acción de entrega y la ubicación](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location): esta comprobación te permite conocer la ubicación de los mensajes de correo electrónico problemáticos.
- [Ver la escala de tiempo del correo electrónico](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email): simplemente busca al equipo de operaciones de seguridad.

#### <a name="see-campaigns-targeting-your-organization"></a>Mira las campañas dirigidas a tu organización

Consulta la imagen más grande con Vistas de campaña en Defender para Office 365, que te ofrece una vista de las campañas de ataque dirigidas a tu organización y su impacto en los usuarios.

- [Identificar las campañas dirigidas](campaigns.md#what-is-a-campaign) a los usuarios.
- [Visualizar el alcance](campaigns.md#campaign-views-in-the-microsoft-365-defender-portal) del ataque.
- [Realizar un seguimiento de la interacción del usuario](campaigns.md#campaign-details) con estos mensajes.

  :::image type="content" source="../../media/mdo-trial-playbook-campaign-details.png" alt-text="Detalles de la campaña en el portal de Microsoft 365 Defender." lightbox="../../media/mdo-trial-playbook-campaign-details.png":::

Mira este vídeo para obtener más información: [Vistas de campaña en Microsoft Defender para Office 365 - YouTube](https://www.youtube.com/watch?v=DvqzzYKu7cQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=14).

#### <a name="use-automation-to-remediate-risks"></a>Usa la automatización para corregir riesgos

Responde de forma eficaz mediante la investigación y respuesta automatizadas (AIR) para revisar, priorizar y responder a las amenazas.

- [Más información](automated-investigation-response-office.md) sobre los cuadernos de prueba de investigación.
- [Ver los detalles y resultados](email-analysis-investigations.md) de una investigación.
- Elimina las amenazas [mediante la aprobación de acciones de corrección](air-remediation-actions.md).

:::image type="content" source="../../media/mdo-trial-playbook-investigation-results.png" alt-text="Resultados de la investigación." lightbox="../../media/mdo-trial-playbook-investigation-results.png":::

### <a name="step-3-advanced-content-in-blocking-mode"></a>Paso 3: Contenido avanzado en modo de bloqueo

#### <a name="dive-deep-into-data-with-query-based-hunting"></a>Profundiza en los datos con la búsqueda basada en consultas

Usa la búsqueda avanzada para escribir reglas de detección personalizadas, inspeccionar proactivamente los eventos de tu entorno y localizar indicadores de amenazas. Explora los datos sin procesar del entorno.

- [Crea reglas de detección personalizadas](../defender/custom-detections-overview.md).
- [Accede a consultas compartidas](../defender/advanced-hunting-shared-queries.md) creadas por otros usuarios.

Mira este vídeo para obtener más información: [Búsqueda de amenazas con Microsoft 365 Defender - YouTube](https://www.youtube.com/watch?v=l3OmH4U6XAs&list=PL3ZTgFEc7Lyt1O81TZol31YXve4e6lyQu&index=4).

#### <a name="train-users-to-spot-threats-by-simulating-attacks"></a>Entrena a los usuarios para detectar amenazas simulando ataques

Proporciona los conocimientos adecuados a los usuarios para que identifiquen amenazas e informar de mensajes sospechosos con el entrenamiento de simulación de ataques en Defender para Office 365.

- [Simula amenazas realistas](attack-simulation-training.md) para identificar a los usuarios vulnerables.
- [Asigna formación](attack-simulation-training.md#assign-training) a los usuarios en función de los resultados de la simulación.
- [Realiza un seguimiento del progreso](attack-simulation-training-insights.md) de la organización en las simulaciones y la finalización de aprendizaje.

  :::image type="content" source="../../media/mdo-trial-playbook-attack-simulation-training-results.png" alt-text="Información sobre el aprendizaje mediante la simulación de ataques en el portal de Microsoft 365 Defender." lightbox="../../media/mdo-trial-playbook-attack-simulation-training-results.png":::

## <a name="auditing-mode"></a>Modo de auditoría

### <a name="step-1-get-started-in-auditing-mode"></a>Paso 1: Introducción al modo de auditoría

#### <a name="start-your-defender-for-office-365-evaluation"></a>Inicio de la evaluación de Defender para Office 365

Una vez completado el [proceso de configuración](try-microsoft-defender-for-office-365.md#set-up-an-evaluation-in-audit-mode), los cambios pueden tardar hasta 2 horas en tomar efecto. Hemos configurado automáticamente las directivas de evaluación preestablecida en su entorno.

Las directivas de evaluación garantizan que no se realice ninguna acción en el correo electrónico detectado por Defender para Office 365.

#### <a name="enable-users-to-report-suspicious-content-in-auditing-mode"></a>Permitir que los usuarios notifiquen contenido sospechoso en modo de auditoría

Defender para Office 365 permite a los usuarios notificar mensajes a sus equipos de seguridad y permite que los administradores envíen mensajes a Microsoft para ser analizados.

- Implementa [el complemento Mensaje de informe o el complemento Notificar suplantación de identidad (phishing)](enable-the-report-message-add-in.md).
- Establece un flujo de trabajo para [Notificar falsos positivos y falsos negativos](report-false-positives-and-false-negatives.md).
- Usa el [Portal de envíos](admin-submission.md).

Mira este vídeo para obtener más información: [Aprender a usar el portal de envíos para enviar mensajes para ser analizados - YouTube](https://www.youtube.com/watch?v=ta5S09Yz6Ks&ab_channel=MicrosoftSecurit).

#### <a name="review-reports-to-understand-the-threat-landscape-in-auditing-mode"></a>Revisar informes para comprender el panorama de amenazas en modo auditoría

Usa las funcionalidades de informe de Defender para Office 365 para obtener más detalles sobre tu entorno.

- El [panel Evaluación](try-microsoft-defender-for-office-365.md#reporting-in-audit-mode) proporciona una vista sencilla de las amenazas detectadas por Defender para Office 365 durante la evaluación.
- Comprende las amenazas recibidas en las herramientas de correo electrónico y de colaboración con el [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).

### <a name="step-2-intermediate-steps-in-auditing-mode"></a>Paso 2: Pasos intermedios en modo auditoría

#### <a name="use-threat-explorer-to-investigate-malicious-email-in-auditing-mode"></a>Usar el Explorador de amenazas para investigar el correo electrónico malintencionado en modo de auditoría

Defender para Office 365 permite investigar las actividades que ponen en peligro a las personas de la organización y tomar medidas para proteger la organización. Puedes hacerlo con el [Explorador de amenazas o (detecciones en tiempo real)](threat-explorer.md)

- [Buscar correo electrónico sospechoso que haya sido entregado](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered): buscar y eliminar mensajes, identificar la dirección IP de un remitente de correo electrónico malintencionado o abrir un incidente para una investigación posterior.
- [Comprobar la acción de entrega y la ubicación](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location): esta comprobación te permite conocer la ubicación de los mensajes de correo electrónico problemáticos.
- [Ver la escala de tiempo del correo electrónico](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email): simplemente busca al equipo de operaciones de seguridad.

#### <a name="convert-to-standard-protection-at-the-end-of-evaluation-period"></a>Convertir en protección estándar al final del período de evaluación

Cuando esté listo para activar las directivas de Defender para Office 365 en producción, puede utilizar "Convertir en protección estándar" dentro de la experiencia administrativa de evaluación para pasar fácilmente a la protección estándar en las [directivas de seguridad preestablecidas](preset-security-policies.md).

1. En la página de **evaluación de Microsoft Defender para Office 365** en <https://security.microsoft.com/atpEvaluation>, haga clic en **Administrar**.

   :::image type="content" source="../../media/mdo-trial-playbook-mdo-evaluation-page.png" alt-text="Haga clic en Administrar en la página de evaluación de Defender para Office 365 en el portal de Microsoft 365 Defender." lightbox="../../media/mdo-trial-playbook-mdo-evaluation-page.png":::

2. En el control flotante que se abre, haga clic en **Convertir a protección estándar**

   :::image type="content" source="../../media/mdo-trial-playbook-manage-flyout.png" alt-text="Haga clic en Convertir a protección estándar en el menú desplegable Administrar en la página de evaluación de Defender para Office 365" lightbox="../../media/mdo-trial-playbook-manage-flyout.png":::. 

3. En el cuadro de diálogo **Convertir en protección estándar** que se abre, haga clic en **Continuar** para iniciar la instalación.

#### <a name="migrate-from-a-third-party-protection-service-or-device-to-defender-for-office-365"></a>Migrar desde un dispositivo o servicio de protección de terceros a Defender para Office 365

Si ya tiene un dispositivo o servicio de protección de terceros que se encuentra delante de Microsoft 365, puede migrar su protección a Microsoft Defender para Office 365 para obtener las ventajas de una experiencia de administración consolidada, un costo potencialmente reducido (con productos que ya paga) y un producto consolidado con protección de seguridad integrada.

Para obtener más información, consulte[Migrar desde un dispositivo o servicio de protección de terceros a Microsoft Defender para Office 365](migrate-to-defender-for-office-365.md).

### <a name="step-3-advanced-content-in-auditing-mode"></a>Paso 3: Contenido avanzado en modo auditoría

#### <a name="train-users-to-spot-threats-by-simulating-attacks-in-auditing-mode"></a>Entrenar a los usuarios para detectar amenazas mediante la simulación de ataques en modo auditoría

Proporciona los conocimientos adecuados a los usuarios para que identifiquen amenazas e informar de mensajes sospechosos con el entrenamiento de simulación de ataques en Defender para Office 365.

- [Simula amenazas realistas](attack-simulation-training.md) para identificar a los usuarios vulnerables.
- [Asigna formación](attack-simulation-training.md#assign-training) a los usuarios en función de los resultados de la simulación.
- [Realiza un seguimiento del progreso](attack-simulation-training-insights.md) de la organización en las simulaciones y la finalización de aprendizaje.

  :::image type="content" source="../../media/mdo-trial-playbook-attack-simulation-training-results.png" alt-text="Información sobre el aprendizaje mediante la simulación de ataques en el portal de Microsoft 365 Defender." lightbox="../../media/mdo-trial-playbook-attack-simulation-training-results.png":::

## <a name="additional-resources"></a>Recursos adicionales

- **Guía interactiva:**¿No estás familiarizado con Defender para Office 365? Revisa la [guía interactiva](https://mslearn.cloudguides.com/guides/Safeguard%20your%20organization%20with%20Microsoft%20Defender%20for%20Office%20365) para saber cómo empezar.
- **Guía de introducción a Fast Track\:[Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/p/?linkid=2197415)
- **Documentos de Microsoft**: Obtén información detallada sobre cómo funciona Defender para Office 365 y la mejor manera de implementarlo para su organización. Visite [Docs](overview.md).
- **Qué incluye**: Para ver todas las características de seguridad del correo electrónico de Office 365 ordenadas por nivel de producto, consulta la [Matriz de características](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability).
- **Por qué elegir Defender para Office 365**: La [hoja de datos de Defender para Office 365](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4FCiy) muestra las 10 razones principales por las que los clientes eligen Microsoft.
