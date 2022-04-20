---
title: Portal de cumplimiento de Microsoft Purview.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
description: Obtenga información sobre el portal de cumplimiento de Microsoft Purview, incluido lo que contiene, cómo obtenerlo y los pasos siguientes.
ms.collection: M365-security-compliance
ms.custom:
- admindeeplinkCOMPLIANCE
- intro-overview
ms.openlocfilehash: 504c5426ccbf2322cc7803fda1b5f396a5cf935c
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64970789"
---
# <a name="microsoft-purview-compliance-portal"></a>Portal de cumplimiento de Microsoft Purview.

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Si está interesado en la posición de cumplimiento de su organización, le encantará el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento de Microsoft Purview</a>. El portal de cumplimiento de Microsoft Purview proporciona fácil acceso a los datos y las herramientas que necesita para administrar las necesidades de cumplimiento de su organización.

Lea este artículo para familiarizarse con el portal de cumplimiento, [cómo acceder a él](#how-do-i-access-the-compliance-portal) y [los pasos siguientes](#next-steps).

[![Página principal del portal de cumplimiento de Microsoft Purview.](../media/m365-compliance-center-home.png)](https://compliance.microsoft.com)

## <a name="welcome-to-microsoft-purview"></a>Bienvenido a Microsoft Purview

Cuando vaya al portal de cumplimiento por primera vez, recibirá el siguiente mensaje de bienvenida:

![Introducción al portal de cumplimiento de Microsoft Purview.](../media/m365-compliance-center-welcome-steps.png)

El banner de bienvenida le ofrece algunos punteros sobre cómo empezar, con los pasos siguientes y una invitación para que nos envíe comentarios.

## <a name="card-section"></a>Sección de la tarjeta

Cuando visite por primera vez el portal de cumplimiento, la sección de la tarjeta de la página principal le muestra de un vistazo cómo está haciendo su organización con el cumplimiento de datos, qué soluciones están disponibles para su organización y un resumen de las alertas activas.

Desde ahí, puede hacer lo siguiente:

- Revise la tarjeta **Administrador de cumplimiento de Microsoft Purview** , que le lleva a la solución [Administrador de cumplimiento](compliance-manager.md) . El Administrador de cumplimiento ayuda a simplificar la forma de administrar el cumplimiento. Calcula una puntuación basada en riesgos que mide el progreso hacia la realización de las acciones recomendadas que ayudan a reducir los riesgos relacionados con la protección de datos y los estándares normativos. También proporciona funcionalidades de flujo de trabajo y asignación de controles integrada para ayudarle a llevar a cabo de forma eficaz acciones de mejora.

    ![Tarjeta del Administrador de cumplimiento Portal de cumplimiento de Microsoft Purview.](../media/m365-compliance-center-compliance-manager-card.png)

- Revise la nueva tarjeta de **catálogo de** soluciones, que se vincula a colecciones de [soluciones integradas](microsoft-365-solution-catalog.md) que puede usar para ayudarle a administrar escenarios de cumplimiento de un extremo a otro. Las funciones y herramientas de una solución pueden incluir una combinación de directivas, alertas, informes y mucho más.

    ![Tarjeta de catálogo de soluciones Portal de cumplimiento de Microsoft Purview.](../media/m365-compliance-center-solution-catalog-card.png)

- Revise la tarjeta **Alertas activas** , que incluye un resumen de las [alertas más activas](alert-policies.md) e incluye un vínculo donde puede ver información más detallada, como Gravedad, Estado, Categoría, etc.

    ![Tarjeta de alertas activas Portal de cumplimiento de Microsoft Purview.](../media/m365-compliance-center-active-alerts-card.png)

También puede usar la característica **Agregar tarjetas** para agregar tarjetas adicionales, como una que muestre el cumplimiento de la aplicación en la nube de su organización y otra que muestre datos sobre los usuarios con archivos compartidos, con vínculos a [Defender for Cloud Apps](/cloud-app-security/) u otras herramientas donde pueda explorar datos.

![Detalles adicionales de la tarjeta del centro de cumplimiento.](../media/m365-compliance-center-additional-cards.png)

## <a name="easy-navigation-to-more-compliance-features-and-capabilities"></a>Navegación sencilla a más características y funcionalidades de cumplimiento

Además de los vínculos de las tarjetas de la página principal, verá un panel de navegación en el lado izquierdo de la pantalla que le proporciona fácil acceso a [las alertas](../security/office-365-security/alerts.md), [informes](reports-in-security-and-compliance.md), [directivas](alert-policies.md), soluciones de cumplimiento y mucho más. Para agregar o quitar opciones para un panel de navegación personalizado, use el control **Personalizar navegación** en el panel de navegación. Se abre la configuración **del panel de navegación Personalizar** para que pueda configurar qué elementos aparecen en el panel de navegación.

<br>

****

|Navegación|Comentarios|
|---|---|
|![Navegación en el portal de cumplimiento de Microsoft Purview.](../media/m365-compliance-center-leftnav.png)|Seleccione **Inicio** para volver a la página principal del portal de cumplimiento. <p> Visite **el Administrador de cumplimiento** para comprobar la puntuación de cumplimiento y empezar a [administrar el cumplimiento](compliance-manager.md) de su organización. <p> Seleccione la sección **Clasificación de datos** para acceder a [clasificadores entrenables, definiciones](classifier-learn-about.md) de [entidades de tipo información confidencial, exploradores](sensitive-information-type-entity-definitions.md) de contenido y [actividad](data-classification-activity-explorer.md) . <p> Seleccione **Conectores de datos** para [configurar conectores](archiving-third-party-data.md) para importar y archivar datos en la suscripción de Microsoft 365. <p> Vaya a **Alertas** para ver y resolver [alertas](alert-policies.md) <p>Visite **Informes** para ver datos sobre el [uso y la retención de etiquetas](sensitivity-labels.md), [coincidencias e invalidaciones](view-the-dlp-reports.md) de directiva DLP, [archivos compartidos](/cloud-app-security/file-filters), [aplicaciones de terceros en uso](/cloud-app-security/discovered-apps), etc. <p> Vaya a **Directivas** para configurar directivas para controlar los datos, administrar dispositivos y recibir [alertas](../security/office-365-security/alerts.md). También puede acceder a las directivas [DLP](dlp-learn-about-dlp.md) y [de retención](retention.md) . <p> Seleccione **Permisos** para administrar quién de su organización tiene acceso al portal de cumplimiento para ver el contenido y completar tareas. <p> Use los vínculos de la sección **Soluciones** para acceder a las soluciones de cumplimiento de su organización. Incluyen: <p> [Catálogo](microsoft-365-solution-catalog.md) <br> Descubra, obtenga información y empiece a usar las soluciones inteligentes de cumplimiento y administración de riesgos disponibles para su organización. <p> [Auditoría](search-the-audit-log-in-security-and-compliance.md) <br> Use el registro de auditoría para investigar problemas comunes de compatibilidad y cumplimiento. <p> [Búsqueda de contenido](search-for-content.md) <br> Use búsqueda de contenido para encontrar rápidamente correo electrónico en buzones de Exchange, documentos en sitios SharePoint y ubicaciones de OneDrive, y conversaciones de mensajería instantánea en Microsoft Teams y Skype Empresarial. <p> [Cumplimiento de las comunicaciones](communication-compliance.md) <br> Minimice los riesgos de comunicación mediante la captura automática de mensajes inadecuados, la investigación de posibles infracciones de directivas y la adopción de medidas para corregirlos. <p> [Más información sobre la prevención de pérdida de datos de Microsoft Purview](dlp-learn-about-dlp.md) <br> Detecte contenido confidencial a medida que se usa y se comparte en toda la organización, en la nube y en los dispositivos, y ayuda a evitar la pérdida accidental de datos. <p> [Solicitudes de interesados](/compliance/regulatory/gdpr-manage-gdpr-data-subject-requests-with-the-dsr-case-tool) <br> Busque y exporte los datos personales de un usuario para ayudarle a responder a las solicitudes del interesado para el Reglamento General de Protección de Datos (RGPD). <p> [eDiscovery](overview-ediscovery-20.md) <br> Expanda esta sección para usar el núcleo y eDiscovery (Premium) para conservar, recopilar, revisar, analizar y exportar contenido que responda a las investigaciones internas y externas de su organización. <p> [Administración del ciclo de vida de los datos](manage-data-governance.md) <br> Administre el ciclo de vida de los datos confidenciales mediante características para importar, almacenar y clasificar datos críticos para la empresa para que pueda conservar lo que necesita y eliminar lo que no. <p> [Protección de la información](information-protection.md) <br> Descubra, clasifique y proteja datos confidenciales y críticos para la empresa a lo largo de su ciclo de vida en toda la organización. <p> [Administración de riesgos internos](insider-risk-management.md) <br> Detecte actividades de riesgo en toda la organización para ayudarle a identificar, investigar y tomar medidas rápidamente sobre riesgos internos y amenazas. <p> [Administración de registros](records-management.md) <br> Administre la retención y eliminación de elementos de alto valor para los requisitos de mantenimiento de registros empresariales, legales o normativos.|
|

## <a name="how-do-i-access-the-compliance-portal"></a>Cómo acceder al portal de cumplimiento?

Para acceder al portal de cumplimiento, vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) e inicie sesión como administrador global, administrador de cumplimiento o administrador de datos de cumplimiento.

## <a name="next-steps"></a>Siguientes pasos

- **Visite el Administrador de cumplimiento de Microsoft Purview** para ver la puntuación de cumplimiento y empezar a administrar el cumplimiento de su organización. Para más información, consulte [Administrador de cumplimiento](compliance-manager.md).

- **Configure directivas de administración de riesgos** internos para ayudar a minimizar los riesgos internos y permitirle detectar, investigar y tomar medidas para actividades de riesgo en su organización. Consulte [Información sobre la administración de riesgos internos](insider-risk-management.md).

- **Revise las directivas de prevención de pérdida de datos de su organización** y realice los cambios necesarios según sea necesario. Para más información, consulte [Información sobre la prevención de pérdida de datos](dlp-learn-about-dlp.md).

- **Familiarícese con y configure Microsoft Defender for Cloud Apps**. Consulte [Inicio rápido: Comenzar con Microsoft Defender for Cloud Apps](/cloud-app-security/getting-started-with-cloud-app-security).

- **Obtenga información y cree directivas de cumplimiento de comunicaciones** para identificar y corregir rápidamente las infracciones de directivas de código de conducta corporativo. Consulte [Más información sobre el cumplimiento de comunicaciones](communication-compliance.md).

- **Visite el portal de cumplimiento con frecuencia** y asegúrese de revisar las alertas o posibles riesgos que surjan. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) e inicie sesión.
