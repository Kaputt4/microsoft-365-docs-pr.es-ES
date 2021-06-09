---
title: Introducción al panel de alertas de prevención de pérdida de datos
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Introducción a la definición y administración de alertas para directivas de prevención de pérdida de datos.
ms.openlocfilehash: ad117eb0c5460b90c92c664f0c233b81d1882327
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843871"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a>Introducción al panel de alertas de prevención de pérdida de datos

Las directivas de prevención de pérdida de datos (DLP) pueden realizar acciones de protección para evitar el uso compartido involuntario de elementos confidenciales. Cuando se hace una acción en un elemento confidencial, se le puede notificar configurando alertas para DLP. En este artículo se muestra cómo definir directivas de alerta enriquecciones vinculadas a las directivas de prevención de pérdida de datos (DLP). Verá cómo usar el panel de administración de alertas [DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) en el Centro de cumplimiento de [Microsoft 365](https://compliance.microsoft.com/) para ver alertas, eventos y metadatos asociados para infracciones de directivas DLP.

Si no es nuevo en las alertas dlp, debe revisar Información sobre el panel de [alertas de](dlp-alerts-dashboard-learn.md) prevención de pérdida de datos

## <a name="before-you-begin"></a>Antes de empezar

Antes de comenzar, asegúrese de que tiene los requisitos previos necesarios:

-   Licencias para el panel de administración de alertas DLP
-   Licencias para opciones de configuración de alertas
-   Funciones

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Licencias para el panel de administración de alertas DLP

Todos los inquilinos elegibles para Office 365 DLP pueden acceder al panel de administración de alertas DLP. Para empezar, debes ser elegible para dlp Office 365 para Exchange Online, SharePoint Online y OneDrive para la Empresa. Para obtener más información acerca de los requisitos de licencia para Office 365 DLP, vea ¿Qué licencias proporcionan los derechos para que un usuario se beneficie [del servicio?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).

Los clientes que usan [DLP](endpoint-dlp-learn-about.md) de extremo que son elegibles para [Teams DLP](dlp-microsoft-teams.md) verán sus alertas de directiva DLP de punto de conexión y Teams de directivas DLP en el panel de administración de alertas dlp.

La **característica de vista previa** de contenido solo está disponible para estas licencias:

- Microsoft 365 (E5)
- Office 365 (E5)
- Complemento de cumplimiento avanzado (E5)
- Microsoft 365 E5/A5 Information Protection and Governance
- Cumplimiento de Microsft 365 E5/A5

### <a name="licensing-for-alert-configuration-options"></a>Licencias para opciones de configuración de alertas

Configuración de alerta de evento **único:** las organizaciones que tienen una suscripción A1, F1 o G1 o una suscripción A3 o G3 solo pueden crear directivas de alerta cuando se desencadena una alerta cada vez que se produce una actividad.

**Configuración de alerta agregada:** para configurar directivas de alerta agregadas basadas en un umbral, debe realizar una de estas configuraciones de licencias:

- Una suscripción A5 o G5
- Una suscripción E1, F1 o G1 o una suscripción A3 o G3 que incluye una de las siguientes características:
    - Protección contra amenazas avanzada de Office 365 (plan 2)
    - Cumplimiento de Microsoft 365 E5
    - Microsoft 365 de complementos de eDiscovery y Audit

### <a name="roles"></a>Funciones


Si desea ver el panel de administración de alertas DLP o editar las opciones de configuración de alertas en una directiva DLP, debe ser miembro de uno de estos grupos de roles:

- Administrador de cumplimiento
- Administrador de datos de cumplimiento
- Administrador de seguridad
- Operador de seguridad
- Lector de seguridad

Para obtener acceso al panel de administración de alertas DLP, necesita:

- Administrar alertas

y cualquiera de estos dos roles:

- Administración de cumplimiento de DLP
- View-Only de cumplimiento dlp

Para obtener acceso a la característica de vista previa de contenido y a las características de contexto y contenido confidencial coincidentes, debe ser miembro de:

- Grupo de roles visor de contenido del Explorador de contenido

que tiene el rol de visor de contenido de clasificación de datos asignado previamente.

## <a name="dlp-alert-configuration"></a>Configuración de alerta DLP

Para obtener información sobre cómo configurar una alerta en la directiva DLP, vea [Where to start with data loss prevention](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention).

### <a name="aggregate-event-alert-configuration"></a>Configuración de alerta de eventos agregados

Si su organización tiene licencia para [opciones de](#licensing-for-alert-configuration-options)configuración de alerta agregadas, verá estas opciones al crear o editar una directiva DLP.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Captura de pantalla que muestra las opciones de los informes de incidentes para los usuarios que son aptos para opciones de configuración de alerta agregadas." border="false":::

Esta configuración permite configurar una directiva para generar una alerta cada vez que una actividad coincide con las condiciones de la directiva o cuando se supera un umbral determinado, en función del número de actividades o en función del volumen de datos exfiltrados.

### <a name="single-event-alert-configuration"></a>Configuración de alerta de evento único

Si su organización tiene licencia para [opciones](#licensing-for-alert-configuration-options)de configuración de alertas de un solo evento, verá estas opciones al crear o editar una directiva DLP. Use esta opción para crear una alerta que se genera cada vez que se produce una coincidencia de reglas DLP.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Captura de pantalla que muestra las opciones de los informes de incidentes para los usuarios que son aptos para opciones de configuración de alertas de un solo evento." border="false":::

## <a name="investigate-a-dlp-alert"></a>Investigar una alerta DLP

Para trabajar con el panel de administración de alertas DLP:

1. En el [centro Microsoft 365 cumplimiento,](https://www.compliance.microsoft.com)vaya a **Prevención de pérdida de datos**.
2. Seleccione la **pestaña Alertas** para ver el panel de alertas dlp.
3. Seleccione una alerta para ver los detalles:

:::image type="content" source="../media/alert-details.png" alt-text="Captura de pantalla que muestra detalles de alertas en el panel de administración de alertas DLP." border="false":::

4. Seleccione la **pestaña Eventos** para ver todos los eventos asociados con la alerta. Puede elegir un evento en particular para ver sus detalles. Para obtener una lista de algunos de los detalles de eventos disponibles, vea [Learn about the data loss prevention Alerts dashboard](dlp-alerts-dashboard-learn.md).
5. Seleccione **Detalles** para abrir la **página Información** general de la alerta. La página de información general proporciona un resumen:
    1. de lo que ocurrió
    1. quién realizó las acciones que provocaron la coincidencia de la directiva
    1. información sobre la directiva coincidente y más 

6. Elija la **pestaña Eventos** para obtener acceso a:
    1. contenido implicado
    1. tipos de información confidencial coincidentes
    1. metadatos

7. Seleccione la **pestaña Tipos de información** confidencial para ver detalles sobre los tipos de información confidencial detectados en el contenido. Los detalles incluyen confianza, recuento y el contenido que coincide con el tipo de información confidencial.

8. Después de investigar la alerta, vuelva a la pestaña Información general, donde puede administrar el triage y administrar la eliminación de la alerta y agregar comentarios. 

- Para ver el historial de administración de flujos de trabajo, elija **Registro de administración**.
- Después de realizar la acción necesaria para la alerta, establezca el estado de la alerta en **Resuelto**.

## <a name="see-also"></a>Consulte también

- [Obtenga información sobre las alertas de prevención de pérdida de datos y el panel de alertas](dlp-alerts-dashboard-learn.md)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)