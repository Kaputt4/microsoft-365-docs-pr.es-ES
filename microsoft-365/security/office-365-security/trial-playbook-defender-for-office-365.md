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
ms.openlocfilehash: f23c45d117735997c219278621be7f314602cd8f
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "65130700"
---
# <a name="trial-playbook-microsoft-defender-for-office-365"></a>Versión de prueba del cuaderno de estrategias: Microsoft Defender para Office 365

Bienvenido a la versión de prueba del cuaderno de estrategias de Microsoft Defender para Office 365. Este cuaderno de estrategias te ayudará a sacarle el máximo partido a tu prueba gratuita de 90 días al enseñarte cómo proteger tu organización con Defender para Office 365. Con las recomendaciones de Microsoft, aprenderás cómo Defender para Office 365 puede ayudarte a definir las directivas de protección, analizar las amenazas de tu organización y responder a los ataques.

:::image type="content" source="../../media/mdo-trial-playbook-what-is-mdo.png" alt-text="Representación gráfica de todos los componentes de Microsoft Defender para Office 365" lightbox="../../media/mdo-trial-playbook-what-is-mdo.png":::

Estas acciones son recomendaciones del equipo de Microsoft Defender sobre las características clave que puedes probar en la prueba de 90 días.

## <a name="step-1-getting-started"></a>Paso 1: Introducción

### <a name="start-your-microsoft-defender-for-office-365-trial"></a>Iniciar la versión de prueba de Microsoft Defender para Office 365

Después de iniciar la prueba y completar el proceso de configuración, los cambios pueden tardar hasta 2 horas en surtir efecto.

Hemos configurado automáticamente las [Directivas de seguridad preestablecidas](preset-security-policies.md) en tu entorno. Estas directivas representan un perfil de protección de línea base adecuado para la mayoría de los usuarios. La protección estándar incluye:

- Vínculos seguros, datos adjuntos seguros y directivas contra la suplantación de identidad que engloban todo el espacio empresarial o el subconjunto de usuarios que hayas elegido durante el proceso de configuración de prueba.
- Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams.
- Protección de vínculos seguros para aplicaciones de Office 365 compatibles.

Mira este vídeo para obtener más información: [Protección contra vínculos malintencionados con Vínculos seguros en Microsoft Defender para Office 365 - YouTube](https://www.youtube.com/watch?v=vhIJ1Veq36Y&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=9).

### <a name="enable-users-to-report-suspicious-content"></a>Permite que los usuarios informen de contenido sospechoso

Defender para Office 365 permite a los usuarios notificar mensajes a sus equipos de seguridad y permite que los administradores envíen mensajes a Microsoft para ser analizados.

- Implementa [el complemento Mensaje de informe o el complemento Notificar suplantación de identidad (phishing)](enable-the-report-message-add-in.md).
- Establece un flujo de trabajo para [Notificar falsos positivos y falsos negativos](report-false-positives-and-false-negatives.md).
- Usa el [Portal de envíos](admin-submission.md).

Mira este vídeo para obtener más información: [Aprender a usar el portal de envíos para enviar mensajes para ser analizados - YouTube](https://www.youtube.com/watch?v=ta5S09Yz6Ks&ab_channel=MicrosoftSecurit).

### <a name="review-reports-to-understand-the-threat-landscape"></a>Revisa informes para entender el panorama de amenazas

Usa las funcionalidades de informe de Defender para Office 365 para obtener más detalles sobre tu entorno.

- Comprende las amenazas recibidas en las herramientas de correo electrónico y de colaboración con el [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).
- Consulta dónde se bloquean las amenazas con el [informe de estado del Flujo de correo](view-email-security-reports.md#mailflow-status-report).
- [Revisa los vínculos](view-reports-for-mdo.md#url-protection-report) que han visto los usuarios o que el sistema ha bloqueado.

:::image type="content" source="../../media/mdo-trial-playbook-reporting.png" alt-text="Correos electrónicos e informes de colaboración en el portal de Microsoft 365 Defender" lightbox="../../media/mdo-trial-playbook-reporting.png":::

## <a name="step-2-intermediate-steps"></a>Paso 2: Pasos intermedios

### <a name="prioritize-focus-on-your-most-targeted-users"></a>Prioriza el enfoque en los principales usuarios de destino

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

### <a name="use-threat-explorer-to-investigate-malicious-email"></a>Usa el Explorador de amenazas para investigar el correo electrónico malintencionado

Defender para Office 365 permite investigar las actividades que ponen en peligro a las personas de la organización y tomar medidas para proteger la organización. Puedes hacerlo con el [Explorador de amenazas o (detecciones en tiempo real)](threat-explorer.md)

- [Buscar correo electrónico sospechoso que haya sido entregado](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered): buscar y eliminar mensajes, identificar la dirección IP de un remitente de correo electrónico malintencionado o abrir un incidente para una investigación posterior.
- [Comprobar la acción de entrega y la ubicación](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location): esta comprobación te permite conocer la ubicación de los mensajes de correo electrónico problemáticos.
- [Ver la escala de tiempo del correo electrónico](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email): simplemente busca al equipo de operaciones de seguridad.

### <a name="see-campaigns-targeting-your-organization"></a>Mira las campañas dirigidas a tu organización

Consulta la imagen más grande con Vistas de campaña en Defender para Office 365, que te ofrece una vista de las campañas de ataque dirigidas a tu organización y su impacto en los usuarios.

- [Identificar las campañas dirigidas](campaigns.md#what-is-a-campaign) a los usuarios.
- [Visualizar el alcance](campaigns.md#campaign-views-in-the-microsoft-365-defender-portal) del ataque.
- [Realizar un seguimiento de la interacción del usuario](campaigns.md#campaign-details) con estos mensajes.

  :::image type="content" source="../../media/mdo-trial-playbook-campaign-details.png" alt-text="Detalles de la campaña en el portal de Microsoft 365 Defender." lightbox="../../media/mdo-trial-playbook-campaign-details.png":::

Mira este vídeo para obtener más información: [Vistas de campaña en Microsoft Defender para Office 365 - YouTube](https://www.youtube.com/watch?v=DvqzzYKu7cQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=14).

### <a name="use-automation-to-remediate-risks"></a>Usa la automatización para corregir riesgos

Responde de forma eficaz mediante la investigación y respuesta automatizadas (AIR) para revisar, priorizar y responder a las amenazas.

- [Más información](automated-investigation-response-office.md) sobre los cuadernos de prueba de investigación.
- [Ver los detalles y resultados](email-analysis-investigations.md) de una investigación.
- Elimina las amenazas [mediante la aprobación de acciones de corrección](air-remediation-actions.md).

:::image type="content" source="../../media/mdo-trial-playbook-investigation-results.png" alt-text="Resultados de la investigación." lightbox="../../media/mdo-trial-playbook-investigation-results.png":::

## <a name="step-3-advanced-content"></a>Paso 3: Contenido avanzado

### <a name="dive-deep-into-data-with-query-based-hunting"></a>Profundiza en los datos con la búsqueda basada en consultas

Usa la búsqueda avanzada para escribir reglas de detección personalizadas, inspeccionar proactivamente los eventos de tu entorno y localizar indicadores de amenazas. Explora los datos sin procesar del entorno.

- [Crea reglas de detección personalizadas](../defender/advanced-hunting-overview.md#get-started-with-advanced-hunting).
- [Accede a consultas compartidas](../defender/advanced-hunting-shared-queries.md) creadas por otros usuarios.

Mira este vídeo para obtener más información: [Búsqueda de amenazas con Microsoft 365 Defender - YouTube](https://www.youtube.com/watch?v=l3OmH4U6XAs&list=PL3ZTgFEc7Lyt1O81TZol31YXve4e6lyQu&index=4).

### <a name="train-users-to-spot-threats-by-simulating-attacks"></a>Entrena a los usuarios para detectar amenazas simulando ataques

Proporciona los conocimientos adecuados a los usuarios para que identifiquen amenazas e informar de mensajes sospechosos con el entrenamiento de simulación de ataques en Defender para Office 365.

- [Simula amenazas realistas](attack-simulation-training.md) para identificar a los usuarios vulnerables.
- [Asigna formación](attack-simulation-training.md#assign-training) a los usuarios en función de los resultados de la simulación.
- [Realiza un seguimiento del progreso](attack-simulation-training-insights.md) de la organización en las simulaciones y la finalización de aprendizaje.

  :::image type="content" source="../../media/mdo-trial-playbook-attack-simulation-training-results.png" alt-text="Información sobre el aprendizaje mediante la simulación de ataques en el portal de Microsoft 365 Defender." lightbox="../../media/mdo-trial-playbook-attack-simulation-training-results.png":::

## <a name="additional-resources"></a>Recursos adicionales

- **Guía interactiva:**¿No estás familiarizado con Defender para Office 365? Revisa la [guía interactiva](https://mslearn.cloudguides.com/guides/Safeguard%20your%20organization%20with%20Microsoft%20Defender%20for%20Office%20365) para saber cómo empezar.
- **Documentos de Microsoft**: Obtén información detallada sobre cómo funciona Defender para Office 365 y la mejor manera de implementarlo para su organización. Visite [Docs](overview.md).
- **Qué incluye**: Para ver todas las características de seguridad del correo electrónico de Office 365 ordenadas por nivel de producto, consulta la [Matriz de características](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability).
- **Por qué elegir Defender para Office 365**: La [hoja de datos de Defender para Office 365](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4FCiy) muestra las 10 razones principales por las que los clientes eligen Microsoft.
