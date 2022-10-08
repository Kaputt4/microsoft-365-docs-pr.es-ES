---
title: Microsoft Defender para Office 365 guía del usuario de prueba
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.collection: m365-security
ms.localizationpriority: high
ms.service: microsoft-365-security
search.appverid:
- MOE150
- MET150
description: Microsoft Defender para Office 365 guía del usuario de prueba de soluciones.
ms.subservice: mdo
ms.custom: trial-playbook
ms.openlocfilehash: 145ebc155b2ae10bfdd2b6cdb05e35746969ad2f
ms.sourcegitcommit: 7828a1e78c3e6bd8d10289f1ad6c8b6769da0966
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2022
ms.locfileid: "68495174"
---
# <a name="trial-user-guide-microsoft-defender-for-office-365"></a>Guía del usuario de prueba: Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a:**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Bienvenido a la guía del usuario de prueba de Microsoft Defender para Office 365! Esta guía del usuario le ayudará a sacar el máximo partido a su evaluación gratuita enseñándole a proteger su organización frente a amenazas malintencionadas que suponen los mensajes de correo electrónico, los vínculos (URL) y las herramientas de colaboración.

## <a name="what-is-defender-for-office-365"></a>¿Qué es Defender para Office 365?

Defender para Office 365 ayuda a las organizaciones a proteger su empresa al ofrecer una lista completa de funcionalidades, incluidas las directivas de protección contra amenazas, los informes, las funcionalidades de investigación y respuesta de amenazas y las funcionalidades automatizadas de investigación y respuesta.

:::image type="content" source="../../media/microsoft-defender-for-office-365.png" alt-text="Microsoft Defender para Office 365 diagrama conceptual." lightbox="../../media/microsoft-defender-for-office-365.png":::

Además de la detección de amenazas avanzadas, el siguiente vídeo muestra cómo las funcionalidades de SecOps de Defender para Office 365 pueden ayudar a su equipo a responder a las amenazas:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMmIe]

### <a name="audit-mode-vs-blocking-mode-for-defender-for-office-365"></a>Modo de auditoría frente a modo de bloqueo para Defender para Office 365

¿Desea que su experiencia de Defender para Office 365 sea activa o pasiva? Estos son los dos modos entre los que puede seleccionar:

- **Modo de auditoría**: se crean *directivas de evaluación* especiales para la protección contra suplantación de identidad (que incluye protección contra suplantación), datos adjuntos seguros y vínculos seguros. Estas directivas de evaluación están configuradas para *detectar* solo amenazas. Defender para Office 365 detecta mensajes dañinos para los informes, pero los mensajes no se actúan sobre ellos (por ejemplo, los mensajes detectados no se ponen en cuarentena). La configuración de estas directivas de evaluación se describe en la sección [Directivas en modo de auditoría](try-microsoft-defender-for-office-365.md#policies-in-audit-mode) más adelante en este artículo.

  El modo auditoría proporciona acceso a informes personalizados para las amenazas detectadas por Defender para Office 365 en la página **Modo de evaluación** en <https://security.microsoft.com/atpEvaluation>.

- **Modo de bloqueo**: la plantilla Estándar para [directivas de seguridad preestablecidas](preset-security-policies.md) se activa y se usa para la prueba, y los usuarios que especifique incluir en la prueba se agregan a la directiva de seguridad preestablecida Estándar. Defender para Office 365 detecta y *toma medidas en* los mensajes *dañinos* (por ejemplo, los mensajes detectados están en cuarentena).

  La selección predeterminada y recomendada es limitar estas directivas de Defender para Office 365 a todos los usuarios de la organización. Pero durante o después de la configuración de la prueba, puede cambiar la asignación de directivas a usuarios, grupos o dominios de correo electrónico específicos en el portal de Microsoft 365 Defender o en [la configuración de directiva asociada a Defender para Office 365 pruebas](try-microsoft-defender-for-office-365.md#policy-settings-associated-with-defender-for-office-365-trials).

  El modo de bloqueo no proporciona informes personalizados para las amenazas detectadas por Defender para Office 365. En su lugar, la información está disponible en los informes normales y las características de investigación de Defender para Office 365 Plan 2.

Un factor clave en el modo de auditoría frente al modo de bloqueo es cómo se entrega el correo electrónico a la organización de Microsoft 365:

- El correo de Internet fluye directamente en Microsoft 365, pero la suscripción actual solo tiene [Exchange Online Protection (EOP)](exchange-online-protection-overview.md) o [Defender para Office 365 Plan 1](overview.md#microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet).

  ![El correo fluye desde Internet a Microsoft 365, con protección contra EOP o Defender para Office 365 Plan 1.](../../media/mdo-trial-mail-flow.png)

  En estos entornos, puede seleccionar **el modo de auditoría** o **el modo de bloqueo**.

- Actualmente usa un servicio o dispositivo de terceros para la protección por correo electrónico de los buzones de Microsoft 365. El correo de Internet fluye a través del servicio de protección antes de su entrega a la organización de Microsoft 365. La protección de Microsoft 365 es lo más baja posible (nunca está completamente desactivada; por ejemplo, siempre se aplica la protección contra malware).

  ![El correo fluye desde Internet a través del dispositivo o servicio de protección de terceros antes de su entrega a Microsoft 365.](../../media/mdo-migration-before.png)

  En estos entornos, solo puede seleccionar **el modo de auditoría** . No es necesario cambiar el flujo de correo (registros MX).

Comencemos

## <a name="blocking-mode"></a>Modo de bloqueo

### <a name="step-1-getting-started-in-blocking-mode"></a>Paso 1: Introducción al modo de bloqueo

#### <a name="start-your-microsoft-defender-for-office-365-trial"></a>Iniciar la versión de prueba de Microsoft Defender para Office 365

Después de iniciar la versión de prueba y completar el [proceso de configuración](try-microsoft-defender-for-office-365.md#set-up-an-evaluation-or-trial-in-blocking-mode), los cambios pueden tardar hasta 2 horas en surtir efecto.

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

Defender for Office 365 enables you to investigate activities that put people in your organization at risk and to take action to protect your organization. You can do this using [Threat Explorer](threat-explorer.md).

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

- [Obtenga más información](automated-investigation-response-office.md) sobre las guías de usuario de investigación.
- [Ver los detalles y resultados](email-analysis-investigations.md) de una investigación.
- Elimina las amenazas [mediante la aprobación de acciones de corrección](air-remediation-actions.md).

:::image type="content" source="../../media/mdo-trial-playbook-investigation-results.png" alt-text="Resultados de la investigación." lightbox="../../media/mdo-trial-playbook-investigation-results.png":::

### <a name="step-3-advanced-content-in-blocking-mode"></a>Paso 3: Contenido avanzado en modo de bloqueo

#### <a name="dive-deep-into-data-with-query-based-hunting"></a>Profundiza en los datos con la búsqueda basada en consultas

Use Advanced hunting to write custom detection rules, proactively inspect events in your environment, and locate threat indicators. Explore raw data in your environment.

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

Una vez completado el [proceso de configuración](try-microsoft-defender-for-office-365.md#set-up-an-evaluation-or-trial-in-audit-mode), los cambios pueden tardar hasta 2 horas en tomar efecto. Hemos configurado automáticamente las directivas de evaluación preestablecida en su entorno.

Las directivas de evaluación garantizan que no se realice ninguna acción en el correo electrónico detectado por Defender para Office 365.

#### <a name="enable-users-to-report-suspicious-content-in-auditing-mode"></a>Permitir que los usuarios notifiquen contenido sospechoso en modo de auditoría

Defender para Office 365 permite a los usuarios notificar mensajes a sus equipos de seguridad y permite que los administradores envíen mensajes a Microsoft para ser analizados.

- Implementa [el complemento Mensaje de informe o el complemento Notificar suplantación de identidad (phishing)](enable-the-report-message-add-in.md).
- Establece un flujo de trabajo para [Notificar falsos positivos y falsos negativos](report-false-positives-and-false-negatives.md).
- Usa el [Portal de envíos](admin-submission.md).

Mira este vídeo para obtener más información: [Aprender a usar el portal de envíos para enviar mensajes para ser analizados - YouTube](https://www.youtube.com/watch?v=ta5S09Yz6Ks&ab_channel=MicrosoftSecurit).

#### <a name="review-reports-to-understand-the-threat-landscape-in-auditing-mode"></a>Revisar informes para comprender el panorama de amenazas en modo auditoría

Usa las funcionalidades de informe de Defender para Office 365 para obtener más detalles sobre tu entorno.

- El [panel Evaluación](try-microsoft-defender-for-office-365.md#reports-for-audit-mode) proporciona una vista sencilla de las amenazas detectadas por Defender para Office 365 durante la evaluación.
- Comprende las amenazas recibidas en las herramientas de correo electrónico y de colaboración con el [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).

### <a name="step-2-intermediate-steps-in-auditing-mode"></a>Paso 2: Pasos intermedios en modo auditoría

#### <a name="use-threat-explorer-to-investigate-malicious-email-in-auditing-mode"></a>Usar el Explorador de amenazas para investigar el correo electrónico malintencionado en modo de auditoría

Defender for Office 365 enables you to investigate activities that put people in your organization at risk and to take action to protect your organization. You can do this using [Threat Explorer](threat-explorer.md).

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
- **Microsoft Defender para Office 365 documentación**: obtenga información detallada sobre cómo funciona Defender para Office 365 y cómo implementarla mejor para su organización. Visite la [documentación de Microsoft Defender para Office 365](defender-for-office-365.md).
- **Qué incluye**: Para ver todas las características de seguridad del correo electrónico de Office 365 ordenadas por nivel de producto, consulta la [Matriz de características](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability).
- **Por qué elegir Defender para Office 365**: La [hoja de datos de Defender para Office 365](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4FCiy) muestra las 10 razones principales por las que los clientes eligen Microsoft.
