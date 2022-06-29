---
title: Novedades de Microsoft Defender para Office 365
description: Obtenga información sobre las nuevas características y funcionalidades disponibles en la versión más reciente de Microsoft Defender para Office 365.
keywords: novedades de Microsoft Defender para Office 365, ga, disponibilidad general, funcionalidades, disponibles, nuevas
search.appverid: met150
ms.sitesec: library
ms.pagetype: security
f1.keywords: NOCSH
ms.author: tracyp
author: msfttracyp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.custom: seo-marvel-apr2020
ms.reviewer: vippand
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 82b23047b8013f9916168d46b5b595b326f6d1e5
ms.sourcegitcommit: c6f1486617b39565bfd8f662ee6ad65a9cefd3e3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66530540"
---
# <a name="whats-new-in-microsoft-defender-for-office-365"></a>Novedades de Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a:**

- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En este artículo se enumeran las nuevas características de la versión más reciente de Microsoft Defender para Office 365. Las características que se encuentran actualmente en versión preliminar se indican con **(versión preliminar).**

Obtenga más información con [este vídeo](https://www.youtube.com/watch?v=Tdz6KfruDGo&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=3).

Para obtener más información sobre las novedades de otros productos de seguridad de Microsoft Defender, consulte:

- [Novedades de Microsoft 365 Defender](../defender/whats-new.md)
- [Novedades de Microsoft Defender para punto de conexión](../defender-endpoint/whats-new-in-microsoft-defender-endpoint.md)
- [Novedades de Microsoft Defender for Identity](/defender-for-identity/whats-new)
- [Novedades de Microsoft Cloud App Security](/cloud-app-security/release-notes)


## <a name="june-2022"></a>Junio de 2022

- [La suplantación permite usar el envío de administrador](allow-block-email-spoof.md#use-admin-submission-in-microsoft-365-defender): cree entradas de remitente suplantadas permitidas mediante la lista de permitidos o bloqueados de inquilinos.

- [La suplantación permite usar el envío de administrador](allow-block-email-spoof.md#create-impersonated-sender-entries): Agregar permite remitentes suplantados mediante la página Envíos de Microsoft 365 Defender.

- [Ver el envío de administrador convertido desde el envío del usuario](admin-submission.md#convert-user-reported-messages-from-the-custom-mailbox-into-an-admin-submission): configure el buzón personalizado para interceptar los mensajes notificados por el usuario sin enviar los mensajes a Microsoft para su análisis.

- [Ver alerta asociada para envíos de usuarios y administradores](admin-submission.md#view-associated-alert-for-user-and-admin-email-submissions): vea la alerta correspondiente para cada mensaje de phish notificado por el usuario y el envío de correo electrónico de administrador. 

- [Protección de suplantación configurable para usuarios y dominios personalizados y un mayor ámbito dentro de directivas predefinidas](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/configurable-impersonation-protection-and-scope-for-preset/ba-p/3294459):
  - (Elija) Aplique directivas estrictas o estándar preestablecidas a toda la organización y evite la molestia de seleccionar usuarios, grupos o dominios de destinatarios específicos, lo que protege a todos los usuarios destinatarios de su organización. 
  - Configure las opciones de protección de suplantación para usuarios personalizados y dominios personalizados dentro de directivas estrictas y estándar preestablecidas y proteja automáticamente a los usuarios de destino y al dominio de destino frente a ataques de suplantación.

- [Simplificación de la experiencia de cuarentena (parte dos) en Microsoft 365 Defender para office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/simplifying-the-quarantine-experience-part-two/ba-p/3354687): resalta características adicionales para que la experiencia de cuarentena sea aún más fácil de usar.

## <a name="april-2022"></a>Abril de 2022

- [Presentación de la tabla URLClickEvents en Microsoft 365 Defender búsqueda avanzada](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/introducing-the-urlclickevents-table-in-advanced-hunting-with/ba-p/3295096): introducción a la tabla UrlClickEvents en la búsqueda avanzada con Microsoft Defender para Office 365.
- [Mejoras de corrección manual del correo electrónico](/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365): llevar las acciones de purga de correo electrónico manual realizadas en Microsoft Defender para Office 365 al Centro de acciones unificado de Microsoft 365 Defender (M365D) mediante una nueva investigación centrada en la acción.
- [Introducción a la protección diferenciada para las cuentas prioritarias en Microsoft Defender para Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/introducing-differentiated-protection-for-priority-accounts-in/ba-p/3283838): Introducción a la disponibilidad general de la protección diferenciada para las cuentas prioritarias. 
 
## <a name="march-2022"></a>Marzo de 2022

- [Simplifica la experiencia de envío en Microsoft Defender para Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/streamlining-the-submissions-experience-in-microsoft-defender/ba-p/3152080): Presentamos el nuevo proceso de envío unificado y simplificado para simplificar tu experiencia.

## <a name="january-2022"></a>Enero de 2022

- [Experiencias de búsqueda e investigación actualizadas para Microsoft Defender para Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/updated-hunting-and-investigation-experiences-for-microsoft/ba-p/3002015): presentación del panel de resumen de correo electrónico para las experiencias en Defender para Office 365, junto con las actualizaciones de la experiencia para el Explorador de amenazas y las detecciones en tiempo real.

## <a name="october-2021"></a>Octubre de 2021

- [Mejora dkim de entrega avanzada](configure-advanced-delivery.md): se ha agregado compatibilidad con la entrada de dominio DKIM como parte de la configuración de simulación de suplantación de identidad de terceros.
- [Seguro de forma predeterminada](secure-by-default.md): extendido seguro de forma predeterminada para las reglas de flujo de correo de Exchange (también conocidas como reglas de transporte).

## <a name="september-2021"></a>Septiembre de 2021

- [Experiencia de informes mejorada en Defender para Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/improving-the-reporting-experience-in-microsoft-defender-for/ba-p/2760898)
- [Directivas de cuarentena](quarantine-policies.md): los administradores pueden configurar un control pormenorizado para el acceso de los destinatarios a los mensajes en cuarentena y personalizar las notificaciones de correo no deseado del usuario final.
  - [Vídeo de la experiencia de administrador](https://youtu.be/vnar4HowfpY)
  - [Vídeo de la experiencia del usuario final](https://youtu.be/s-vozLO43rI)
  - Otras nuevas funcionalidades que llegan a la experiencia de cuarentena se describen en esta entrada de blog: [Simplificación de la experiencia de cuarentena](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/simplifying-the-quarantine-experience/ba-p/2676388).
- El redireccionamiento del portal comienza de forma predeterminada y redirige a los usuarios desde Cumplimiento de seguridad & a Microsoft 365 Defender <https://security.microsoft.com>. Para obtener más información sobre esto, vea: [Redirigir cuentas desde Office 365 Security & Compliance Center a Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection)

## <a name="august-2021"></a>Agosto de 2021

- [Administración revisión de los mensajes notificados](admin-review-reported-message.md): los administradores ahora pueden enviar mensajes con plantilla de vuelta a los usuarios finales después de revisar los mensajes notificados. Las plantillas se pueden personalizar para su organización y también en función del veredicto del administrador.
- [Agregar permite en la lista de permitidos o bloqueados de inquilinos](manage-tenant-allows.md): ahora puede agregar entradas permitidas a la lista de permitidos o bloqueados de inquilinos si el mensaje bloqueado se envió como parte del proceso de envío del administrador. En función de la naturaleza del bloque, la dirección URL, el archivo o el remitente enviados se agregarán a la lista de permitidos o bloqueados de inquilinos. En la mayoría de los casos, los permite se agregan para dar al sistema algún tiempo y permitirlo naturalmente si se garantiza. En algunos casos, Microsoft administra el permiso para usted.

## <a name="july-2021"></a>Julio de 2021

- [Mejoras en el análisis de correo electrónico en investigaciones automatizadas](email-analysis-investigations.md)
- [Entrega avanzada](configure-advanced-delivery.md): introducción a una nueva funcionalidad para configurar la entrega de simulaciones de suplantación de identidad (phishing) de terceros a los usuarios y mensajes sin filtrar a buzones de operaciones de seguridad.
- [Vínculos seguros para Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams)
- Nuevas directivas de alerta para los siguientes escenarios: buzones en peligro, suplantación de identidad de formularios, correos malintencionados entregados debido a invalidaciones y redondeo de ZAP
  - Actividad de reenvío de correo electrónico sospechoso
  - El usuario no puede compartir formularios ni recopilar respuestas
  - Formulario bloqueado debido a un posible intento de suplantación de identidad (phishing)
  - Formulario marcado y confirmado como suplantación de identidad (phishing)
  - [Nuevas directivas de alertas para ZAP](../../compliance/new-defender-alert-policies.md)
- las alertas de Microsoft Defender para Office 365 ahora se integran en Microsoft 365 Defender: [Microsoft 365 Defender cola de alertas unificadas y cola de alertas unificadas](../defender/investigate-alerts.md)
- [Las etiquetas de usuario](user-tags.md) ahora se integran en Microsoft Defender para Office 365 experiencias de alertas, como: la cola de alertas y los detalles de Office 365 Security & Compliance y el ámbito de las directivas de alerta personalizadas a las etiquetas de usuario para crear directivas de alerta de destino.
  - Las etiquetas también están disponibles en la cola de alertas unificada en el portal de Microsoft 365 Defender (Microsoft Defender para Office 365 plan 2)

## <a name="june-2021"></a>Junio de 2021

- Nueva configuración de la sugerencia de seguridad de primer contacto dentro de las directivas contra suplantación de identidad (phishing). Esta sugerencia de seguridad se muestra cuando los destinatarios reciben por primera vez un correo electrónico de un remitente o no suelen recibir correo electrónico de un remitente. Para obtener más información sobre esta configuración y cómo configurarla, consulte los artículos siguientes:
  - [Primer consejo de seguridad de contacto](set-up-anti-phishing-policies.md#first-contact-safety-tip)
  - [Configuración de directivas contra phishing en EOP](configure-anti-phishing-policies-eop.md)
  - [Configuración de directivas contra phishing en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md)

## <a name="aprilmay-2021"></a>Abril/mayo de 2021

- [Página de entidad de correo electrónico](mdo-email-entity-page.md): una vista unificada en 360 grados de un correo electrónico con información enriquecida sobre amenazas, autenticación y detecciones, detalles de detonación y una experiencia de vista previa de correo electrónico completamente nueva.
- [Office 365 Management API](/office/office-365-management-api/office-365-management-activity-api-schema#email-message-events): Novedades a EmailEvents (RecordType 28) para agregar la acción de entrega, las ubicaciones de entrega originales y más recientes y los detalles de detección actualizados.
- [Análisis de amenazas para Defender para Office 365](/microsoft-365/security/defender/threat-analytics): vea actores de amenazas activos, técnicas populares y superficies de ataque, junto con amplios informes de investigadores de Microsoft sobre campañas en curso.

## <a name="februarymarch-2021"></a>Febrero/marzo de 2021

- Integración del identificador de alerta (búsqueda mediante id. de alerta y navegación Alert-Explorer) en [experiencias de búsqueda](threat-explorer.md)
- Aumento de los límites de exportación de registros de 9990 a 200 000 en [experiencias de búsqueda](threat-explorer.md)
- Ampliación de la retención de datos del Explorador (y detecciones en tiempo real) y el límite de búsqueda para inquilinos de prueba de 7 (límite anterior) a 30 días en [experiencias de búsqueda](threat-explorer.md)
- Nuevas dinámicas de búsqueda denominadas **Dominio suplantado** y **Usuario suplantado** en el Explorador (y detecciones en tiempo real) para buscar ataques de suplantación contra usuarios o dominios protegidos. Para obtener más información, consulte [los detalles](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains). (Microsoft Defender para Office 365 Plan 1 o Plan 2)

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Plan 1 y Plan 2 de Microsoft Defender para Office 365

¿Sabías que Microsoft Defender para Office 365 está disponible en dos planes? [Obtenga más información sobre lo que incluye cada plan](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2).

## <a name="see-also"></a>Vea también

- [Hoja de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap)
- [Descripción del servicio Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
