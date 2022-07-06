---
title: Introducción al panel Alertas DLP
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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
description: Empiece a definir y administrar alertas para directivas de prevención de pérdida de datos.
ms.openlocfilehash: de980fadbc6b6091a0257c032dacab4220704f62
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66625465"
---
# <a name="get-started-with-the-data-loss-prevention-alerts-dashboard"></a>Introducción al panel alertas de prevención de pérdida de datos

las directivas de Prevención de pérdida de datos de Microsoft Purview (DLP) pueden tomar medidas de protección para evitar el uso compartido involuntario de elementos confidenciales. Cuando se realiza una acción en un elemento confidencial, se le puede notificar mediante la configuración de alertas para DLP. En este artículo se muestra cómo definir directivas de alerta enriquecidas vinculadas a las directivas de prevención de pérdida de datos (DLP). Verá cómo usar el [panel de administración de alertas DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a> para ver alertas, eventos y metadatos asociados para infracciones de directiva DLP.

Si no está familiarizado con las alertas DLP, debe revisar [el panel De información sobre las alertas de prevención de pérdida de datos](dlp-alerts-dashboard-learn.md).

## <a name="before-you-begin"></a>Antes de empezar

Antes de empezar, asegúrese de que tiene los requisitos previos necesarios:

-   Licencias para el panel de administración de alertas DLP
-   Licencias para opciones de configuración de alertas
-   Funciones

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Licencias para el panel de administración de alertas DLP

Todos los inquilinos aptos para DLP pueden acceder al panel de administración de alertas DLP. Para empezar, debe ser apto para DLP de Microsoft Purview para Exchange Online, SharePoint Online y OneDrive para la Empresa. Para obtener más información sobre los requisitos de licencia para DLP, consulte [¿Qué licencias proporcionan los derechos para que un usuario se beneficie del servicio?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).

Los clientes que usan [DLP de punto de conexión](endpoint-dlp-learn-about.md) que son aptos para DLP de [Teams](dlp-microsoft-teams.md) verán sus alertas de directiva DLP de punto de conexión y las alertas de directiva DLP de Teams en el panel de administración de alertas DLP.

La característica de **vista previa de contenido** solo está disponible para estas licencias:

- Microsoft 365 (E5)
- Office 365 (E5)
- Complemento de cumplimiento avanzado (E5)
- Gobernanza e Information Protection de Microsoft 365 E5/A5
- Cumplimiento de Microsoft 365 E5/A5 

### <a name="licensing-for-alert-configuration-options"></a>Licencias para opciones de configuración de alertas

**Configuración de alertas de evento único**: las organizaciones que tienen una suscripción E1, F1 o G1 o una suscripción E3 o G3 solo pueden crear directivas de alertas cuando se desencadena una alerta cada vez que se produce una actividad.

**Configuración de alerta agregada**: para configurar directivas de alerta agregadas en función de un umbral, debe tener una de estas configuraciones de licencia:

- Una suscripción A5 o G5
- Una suscripción E1, F1 o G1 o una suscripción E3 o G3 que incluya una de las siguientes características:
    - Protección contra amenazas avanzada de Office 365 (plan 2)
    - Cumplimiento de Microsoft 365 E5
    - Licencia de complemento de auditoría y exhibición de documentos electrónicos de Microsoft 365

### <a name="roles"></a>Funciones

Si desea ver el panel de administración de alertas DLP o editar las opciones de configuración de alertas en una directiva DLP, debe ser miembro de uno de estos grupos de roles:

- Administrador de cumplimiento
- Administrador de datos de cumplimiento
- Administrador de seguridad
- Operador de seguridad
- Lector de seguridad

Para acceder al panel de administración de alertas DLP, necesita lo siguiente:

- Administrar alertas

y cualquiera de estos dos roles:

- Administración de cumplimiento de DLP
- View-Only administración de cumplimiento de DLP

Para acceder a la característica De vista previa de contenido y a las características de contenido confidencial y contexto coincidentes, debe ser miembro de:

- Grupo de roles visor de contenido del Explorador de contenido

que tiene asignado previamente el rol de visor de contenido de clasificación de datos.

### <a name="roles-and-role-groups-in-preview"></a>Roles y grupos de roles en la versión preliminar

Hay roles y grupos de roles en la versión preliminar que puede probar para ajustar los controles de acceso.

Esta es una lista de los roles aplicables que se encuentran en versión preliminar. Para obtener más información, consulte [Roles en el Centro de seguridad y cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)

- Administrador de Information Protection
- Analista de Information Protection
- Investigador de protección de información
- Lector de protección de información

Esta es una lista de los grupos de roles aplicables que se encuentran en versión preliminar. Para obtener más información, consulte [Grupos de roles en el Centro de seguridad y cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#role-groups-in-the-security--compliance-center)

- Protección de la información
- Administradores de Information Protection
- Analistas de Information Protection
- Investigadores de Information Protection
- Lectores de Information Protection

## <a name="dlp-alert-configuration"></a>Configuración de alertas DLP

Para obtener información sobre cómo configurar una alerta en la directiva DLP, consulte [Dónde empezar con la prevención de pérdida de datos](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention).

> [!IMPORTANT]
> La configuración de la directiva de retención de registros de auditoría de las organizaciones controla cuánto tiempo permanece visible una alerta en la consola. Consulte [Administración de directivas de retención de registros de auditoría](audit-log-retention-policies.md#manage-audit-log-retention-policies) para obtener más información.

### <a name="aggregate-event-alert-configuration"></a>Configuración de alertas de eventos agregados

Si su organización tiene licencia para [las opciones de configuración de alertas agregadas](#licensing-for-alert-configuration-options), verá estas opciones al crear o editar una directiva DLP.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Captura de pantalla que muestra las opciones de informes de incidentes para los usuarios que son aptos para las opciones de configuración de alerta agregada." border="false":::

Esta configuración permite configurar una directiva para generar una alerta cada vez que una actividad coincide con las condiciones de la directiva o cuando se supera un umbral determinado, en función del número de actividades o en función del volumen de datos filtrados.

### <a name="single-event-alert-configuration"></a>Configuración de alertas de evento único

Si su organización tiene licencia para [las opciones de configuración de alertas de evento único](#licensing-for-alert-configuration-options), verá estas opciones al crear o editar una directiva DLP. Use esta opción para crear una alerta que se genera cada vez que se produce una coincidencia de regla DLP.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Captura de pantalla que muestra las opciones de informes de incidentes para los usuarios que son aptos para las opciones de configuración de alertas de un solo evento." border="false":::

## <a name="investigate-a-dlp-alert"></a>Investigación de una alerta DLP

Para trabajar con el panel de administración de alertas DLP:

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a>, vaya a **Prevención de pérdida de datos**.
2. Seleccione la pestaña **Alertas** para ver el panel de alertas DLP.
3. Seleccione una alerta para ver los detalles:

:::image type="content" source="../media/alert-details.png" alt-text="Captura de pantalla que muestra los detalles de la alerta en el panel de administración de alertas DLP." border="false":::

4. Seleccione la pestaña **Eventos** para ver todos los eventos asociados a la alerta. Puede elegir un evento determinado para ver sus detalles. Para obtener una lista de algunos de los detalles del evento disponibles, consulte [El panel De alertas de prevención de pérdida de datos](dlp-alerts-dashboard-learn.md).
5. Seleccione **Detalles** para abrir la página **Información general** de la alerta. La página de información general proporciona un resumen:
    1. de lo que pasó
    1. quién realizó las acciones que provocaron la coincidencia de directiva
    1. información sobre la directiva coincidente y mucho más 

6. Elija la pestaña **Eventos** para acceder a:
    1. contenido implicado
    1. tipos de información confidencial coincidentes
    1. Metadatos

7. Seleccione la pestaña **Tipos de información confidencial** para ver detalles sobre los tipos de información confidencial detectados en el contenido. Los detalles incluyen la confianza, el recuento y el contenido que coincide con el tipo de información confidencial.

8. Después de investigar la alerta, vuelva a la pestaña **Información general** , donde puede administrar la evaluación de prioridades y administrar la eliminación de la alerta y agregar comentarios.

- Para ver el historial de la administración de flujos de trabajo, elija **Registro de administración**.
- Después de realizar la acción necesaria para la alerta, establezca el estado de la alerta en **Resuelto**.

## <a name="see-also"></a>Vea también

- [Más información sobre las alertas de prevención de pérdida de datos y el panel de alertas](dlp-alerts-dashboard-learn.md)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
