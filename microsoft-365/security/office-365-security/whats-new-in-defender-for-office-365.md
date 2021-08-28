---
title: Novedades de Microsoft Defender para Office 365
description: Obtenga información sobre las nuevas características y funcionalidades disponibles en la versión más reciente de Microsoft Defender para Office 365.
keywords: novedades de Microsoft Defender para Office 365, ga, disponible en general, funcionalidades, disponible, nuevo
search.appverid: met150
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.date: 07/27/2021
ms.custom: seo-marvel-apr2020
ms.reviewer: vippand
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eab119de2f4058d853a85c6ec5ba3a99056b595e
ms.sourcegitcommit: d016e3bd30c0dd73c4cd3d804c0b6941b5eb3e87
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2021
ms.locfileid: "58684081"
---
# <a name="whats-new-in-microsoft-defender-for-office-365"></a>Novedades de Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En este artículo se enumeran las nuevas características de la versión más reciente de Microsoft Defender para Office 365. Las características que están actualmente en versión preliminar se indican con **(versión preliminar)**.

Obtenga más información con [este vídeo](https://www.youtube.com/watch?v=Tdz6KfruDGo&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=3).

> [!TIP]
> ¿Aún no tiene Microsoft Defender para Office 365? [Póngase en contacto con ventas para iniciar una versión de prueba.](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)

## <a name="september-2021"></a>Septiembre de 2021

- [Directivas de cuarentena:](quarantine-policies.md)los administradores pueden configurar un control pormenorizado para el acceso de los destinatarios a los mensajes en cuarentena y personalizar las notificaciones de correo no deseado del usuario final.
  - [Vídeo de la experiencia de administrador](https://youtu.be/vnar4HowfpY)
  - [Vídeo de la experiencia del usuario final](https://youtu.be/s-vozLO43rI)
  - Otras nuevas funcionalidades que llegan a la experiencia de cuarentena se describen en esta entrada de blog: [Simplificación de la experiencia de cuarentena](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/simplifying-the-quarantine-experience/ba-p/2676388).

## <a name="august-2021"></a>Agosto de 2021

- [Revisión de administrador para los mensajes notificados:](admin-review-reported-message.md)los administradores ahora pueden enviar mensajes con plantilla de vuelta a los usuarios finales después de revisar los mensajes notificados. Las plantillas se pueden personalizar para su organización y también en función del veredicto del administrador.
- Agregar permite en la lista de inquilinos [permitir/bloquear:](manage-tenant-allows.md)ahora puede agregar entradas de permitido a la lista de inquilinos permitidos o bloqueados si el mensaje bloqueado se envió como parte del proceso de envío de administrador. Según la naturaleza del bloque, la dirección URL, el archivo y/o la opción de remitente enviadas se agregarán a la lista de inquilinos permitidos o bloqueados. En la mayoría de los casos, se agregan los permitidos para dar al sistema algo de tiempo y permitirlo de forma natural si se garantiza. En algunos casos, Microsoft administra la opción para usted.

## <a name="july-2021"></a>Julio de 2021

- [Mejoras en el análisis de correo electrónico en investigaciones automatizadas](email-analysis-investigations.md)
- [Entrega avanzada:](configure-advanced-delivery.md)introducción a una nueva funcionalidad para configurar la entrega de simulaciones de suplantación de identidad de terceros a los usuarios y mensajes sin filtrar en buzones de operaciones de seguridad.
- [Caja fuerte Vínculos para Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams)
- Nuevas directivas de alerta para los siguientes escenarios: buzones en peligro, phishing de formularios, correos malintencionados entregados debido a invalidaciones y redondeo de ZAP
  - Actividad de reenvío de correo electrónico sospechoso
  - El usuario no puede compartir formularios y recopilar respuestas
  - Formulario bloqueado debido a un posible intento de suplantación de identidad
  - Formulario marcado y confirmado como suplantación de identidad
  - [Nuevas directivas de alerta para ZAP](../../compliance/new-defender-alert-policies.md)
- Las alertas de Microsoft Defender para Office 365 están ahora integradas en Microsoft 365 Defender: Microsoft 365 Defender cola de alertas unificadas y [cola de alertas unificadas](../defender/investigate-alerts.md)
- [](user-tags.md) Las etiquetas de usuario ahora se integran en Microsoft Defender para obtener experiencias de alerta de Office 365, incluidos: la cola de alertas y los detalles de Office 365 Security & Compliance y el ámbito de las directivas de alerta personalizadas para las etiquetas de usuario para crear directivas de alertas dirigidas. 
  - Las etiquetas también están disponibles en la cola de alertas unificadas en el centro de Microsoft 365 Defender (Microsoft Defender para Office 365 Plan 2)

## <a name="june-2021"></a>Junio de 2021

- Nueva configuración del primer contacto consejo de seguridad dentro de las directivas contra suplantación de identidad. Este consejo de seguridad se muestra cuando los destinatarios reciben por primera vez un correo electrónico de un remitente o no suelen recibir correo electrónico de un remitente. Para obtener más información sobre esta configuración y cómo configurarla, consulte los siguientes artículos:
  - [Primer contacto consejo de seguridad](set-up-anti-phishing-policies.md#first-contact-safety-tip)
  - [Configuración de directivas contra phishing en EOP](configure-anti-phishing-policies-eop.md)
  - [Configurar directivas contra suplantación de identidad en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md)

## <a name="aprilmay-2021"></a>Abril/mayo de 2021

- Página [de](mdo-email-entity-page.md)entidad de correo electrónico: una vista unificada de 360 grados de un correo electrónico con información enriquecida sobre amenazas, autenticación y detecciones, detalles de detonación y una nueva experiencia de vista previa de correo electrónico.
- Office 365 API de [administración:](/office/office-365-management-api/office-365-management-activity-api-schema#email-message-events)actualizaciones de EmailEvents (RecordType 28) para agregar acciones de entrega, ubicaciones de entrega originales y más recientes y detalles de detección actualizados.
- Análisis de amenazas para [Defender para Office 365:](/microsoft-365/security/defender/threat-analytics)ver actores de amenazas activas, técnicas populares y superficies de ataque, junto con amplios informes de investigadores de Microsoft en torno a campañas en curso.

## <a name="februarymarch-2021"></a>Febrero/marzo de 2021

- Integración de id. de alerta (búsqueda mediante identificador de alerta y Alert-Explorer navegación) en [experiencias de búsqueda](threat-explorer.md)
- Aumentar los límites de exportación de registros de 9990 a 200.000 en [experiencias de búsqueda](threat-explorer.md)
- Ampliar el límite de búsqueda y retención de datos del Explorador (y detecciones en tiempo real) para los inquilinos de prueba de 7 (límite anterior) a 30 días en experiencias de [búsqueda](threat-explorer.md)
- Nuevos pivotes de búsqueda denominados **Dominio** suplantado y Usuario suplantado en el Explorador (y detecciones en tiempo real) para buscar ataques de suplantación contra usuarios o dominios protegidos.  Para obtener más información, vea [detalles](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains). (Microsoft Defender para Office 365 Plan 1 o Plan 2)

## <a name="december-2020"></a>Diciembre de 2020

- [Proteger de forma predeterminada en Office 365](secure-by-default.md)
- Mejoras de investigación automatizadas en: alertas generales para investigaciones de correo electrónico desencadenadas manualmente, tratar los cambios de buzones como una categoría de entidad independiente, quitar acciones de bloqueo de direcciones URL redundantes y crear clústeres de correo electrónico salientes para investigaciones comprometidas por el usuario.

## <a name="november-2020"></a>Noviembre de 2020

- Límites de exportación actualizados en Review > Action Center > Remediation from Mail Submission and Action Log (Defender for Office 365 Plan 2)

## <a name="septemberoctober-2020"></a>Septiembre/octubre de 2020

- Nuevo primer contacto consejo de seguridad cuando los destinatarios reciben por primera vez un correo electrónico de un remitente o no suelen recibir correo electrónico de un remitente. Para obtener más información sobre esta configuración y cómo configurarla mediante Exchange de flujo de correo (también conocidas como reglas de [transporte),](set-up-anti-phishing-policies.md#first-contact-safety-tip)vea First contact consejo de seguridad .
- [Comprobar las directivas con el Analizador de configuración](configuration-analyzer-for-security-policies.md)
- [Capacidades extendidas](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) en el Explorador de amenazas, incluidos los principales usuarios de destino, las reglas de transporte y los conectores (Defender para obtener información Office 365 en el Explorador de amenazas [(el](threat-explorer.md) correo electrónico se ha permitido o bloqueado mediante la directiva de inquilino/usuario) (Defender for Office 365 Plan 2)
- Eliminar amenazas de url en el Explorador [de](threat-explorer.md#threats-in-urls) amenazas (malware, phish, correo no deseado o ninguno) (Defender for Office 365 Plan 2)
- [Mejoras en el Explorador de](threat-explorer.md#improvements-to-the-threat-hunting-experience-upcoming) amenazas de experiencia de búsqueda con actualizaciones en torno a amenazas, acciones adicionales, ubicaciones de entrega y vista escala de tiempo actualizada (Defender para Office 365 plan 2)

## <a name="julyaugust-2020"></a>Julio/agosto de 2020

- [Experimentar mejoras en la experiencia de búsqueda](threat-explorer.md#improvements-to-threat-hunting-experience) (Microsoft Defender para Office 365 Plan 1 o Plan 2)
- [Aplicar fácilmente la configuración recomendada mediante directivas de seguridad preestablecidas](preset-security-policies.md)

## <a name="marchapril-2020"></a>Marzo/abril de 2020

- La capacidad de abordar [cuentas de usuario](address-compromised-users-quickly.md) comprometidas con investigación y respuesta automatizadas ahora está disponible en general. (Microsoft Defender para Office 365 plan 2)

## <a name="januaryfebruary-2020"></a>Enero/Febrero de 2020

- [Disponibilidad general de vistas de campaña en Microsoft Defender para Office 365](campaigns.md) (Microsoft Defender para Office 365 plan 2)
- Mejoras en el [Explorador de](threat-explorer.md) amenazas para permitir que los equipos de operaciones de seguridad busquen y filtren en varios campos mientras investigan el correo [electrónico](investigate-malicious-email-that-was-delivered.md): (Microsoft Defender para Office 365 Plan 2)
  - Ubicación de entrega y acciones especiales
  - Direccionalidad (entrante, saliente o intra-org)
  - Filtros NO avanzados (se trata de opciones avanzadas de filtrado que incluyen que no contienen, no incluyen, etc.)
  - Filtros de hora granulares (día, hora, media hora)

- El **widget Incidentes es** ahora el widget Centro **de** acciones. (Para ver los widgets de seguridad en el Centro de seguridad & cumplimiento, vaya a **Administración de amenazas** \> **Revisar**.) (Microsoft Defender para Office 365 plan 2)

- [Caja fuerte documentos en Microsoft 365](safe-docs.md) **(versión preliminar)**

## <a name="december-2019"></a>Diciembre de 2019

- [Exportar datos de clic de dirección URL para análisis](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) sin conexión (Microsoft Defender para Office 365 Plan 1 o Plan 2)

- [Usar vistas de campaña en Microsoft Defender para Office 365 (**versión preliminar**)](campaigns.md) (Microsoft Defender para Office 365 Plan 2)

## <a name="november-2019"></a>Noviembre de 2019

- [Consulte las nuevas capacidades de detección](address-compromised-users-quickly.md) y respuesta de usuarios comprometidas (**versión** preliminar ) (Microsoft Defender para Office 365 plan 2)

## <a name="september-2019"></a>Septiembre de 2019

- [Emplear capacidades automatizadas de investigación y respuesta](automated-investigation-response-office.md) (Microsoft Defender para Office 365 Plan 2)

- [Integrar con Microsoft Defender para Office 365 de](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) investigación y respuesta automatizadas mediante la API de actividad de administración Office 365 (Defender para Office 365 Plan 2)

- [Ver los encabezados de correo electrónico y descargar el](investigate-malicious-email-that-was-delivered.md) cuerpo del correo electrónico (Microsoft Defender para Office 365 Plan 1 o Plan 2)

## <a name="august-2019"></a>Agosto de 2019

- [Ver la escala de tiempo del correo](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email) electrónico (Microsoft Defender para Office 365 Plan 1 o Plan 2)

## <a name="july-2019"></a>Julio de 2019

- [Comprobar la acción de entrega y la ubicación de los](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location) mensajes de correo electrónico (Microsoft Defender para Office 365 plan 1 o 2)

## <a name="june-2019"></a>Junio de 2019

- [Ver direcciones URL de suplantación de](threat-explorer.md#view-phishing-url-and-click-verdict-data) identidad y hacer clic en datos de veredicto (Microsoft Defender para Office 365 Plan 1 o Plan 2)

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Plan 1 y Plan 2 de Microsoft Defender para Office 365

¿Sabía que Microsoft Defender para Office 365 está disponible en dos planes? [Obtenga más información sobre lo que cada plan incluye](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2).

## <a name="see-also"></a>Consulte también

[Microsoft 365 guía básica](https://www.microsoft.com/microsoft-365/roadmap)

[Descripción del servicio Office 365 Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
