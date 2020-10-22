---
title: Configurar y ver alertas para directivas de DLP (versión preliminar)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 10/15/2020
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
description: Obtenga información sobre cómo definir y administrar las alertas de las directivas de DLP.
ms.openlocfilehash: addf46b27575f1a1cc062949aedb7ecdecaf7286
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651478"
---
# <a name="configure-and-view-alerts-for-dlp-polices-preview"></a>Configurar y ver alertas para directivas de DLP (versión preliminar)

En este artículo se muestra cómo definir directivas de alertas enriquecidas que se vinculan a las directivas de prevención de pérdida de datos (DLP). Verá cómo usar el nuevo panel de administración de alertas de DLP en el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/) para ver alertas, eventos y metadatos asociados para infracciones de directivas de DLP.

## <a name="features"></a>Características

Las siguientes características forman parte de esta vista previa:

-   **Panel de administración de alertas de DLP**: en el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), este panel muestra alertas para directivas DLP que se aplican en las siguientes cargas de trabajo:

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   Dispositivos
-   **Opciones de configuración de alertas avanzadas**: estas opciones forman parte del flujo de creación de directivas de DLP. Úselos para crear configuraciones de alertas enriquecidas. Puede crear una alerta de evento único o una alerta agregada, según el número de eventos o el tamaño de los datos perdidos.

## <a name="before-you-begin"></a>Antes de empezar

Antes de empezar, asegúrese de que tiene los requisitos previos necesarios:

-   Licencias para el panel de administración de alertas de DLP
-   Licencias para opciones de configuración de alertas
-   Roles

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Licencias para el panel de administración de alertas de DLP

Todos los inquilinos elegibles para Office 365 DLP pueden tener acceso al nuevo panel de administración de alertas de DLP. Para empezar, debe ser elegible para Office 365 DLP para Exchange Online, SharePoint Online y OneDrive para la empresa. Para obtener más información sobre los requisitos de licencia para la DLP de Office 365, vea [¿Qué licencias proporcionan los derechos de un usuario para beneficiarse del servicio?](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).

Los clientes que participan en la versión preliminar pública de [DLP de DLP](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide) o que son aptos para la DLP de Microsoft [Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams?view=o365-worldwide) verán sus alertas de directiva de DLP de punto de conexión y de directivas de DLP en el panel de administración de alertas de DLP.

### <a name="licensing-for-alert-configuration-options"></a>Licencias para opciones de configuración de alertas

-   **Configuración de alertas de evento único**: las organizaciones que tienen una suscripción a E1, F1 o G1 o una suscripción a E3 o G3 pueden crear directivas de alerta solo cuando se produce una alerta cada vez que se produce una actividad.
-   **Configuración de alerta agregada**: para configurar directivas de alerta agregadas en función de un umbral, debe tener una de las siguientes configuraciones:
    -   Una suscripción a E5 o G5
    -   Una suscripción a E1, F1, G1 o una suscripción a E3 o G3 que incluya una de las siguientes características:
        -   Protección contra amenazas avanzada de Office 365 (plan 2)
        -   Cumplimiento de Microsoft 365 E5
        -   Licencia de Microsoft 365 eDiscovery y el complemento de auditoría

### <a name="roles"></a>Roles

Si desea ver el panel de administración de alertas de DLP o editar las opciones de configuración de alertas en una directiva DLP, debe pertenecer a uno de estos grupos de roles:

-   Administrador de cumplimiento
-   Administrador de datos de cumplimiento
-   Administrador de seguridad
-   Operador de seguridad
-   Lector de seguridad

Para acceder al panel de administración de alertas de DLP, necesita el rol administrar alertas y cualquiera de los siguientes roles:

-   Administración de cumplimiento de DLP
-   View-Only la administración de cumplimiento de DLP

## <a name="alert-configuration-experience"></a>Experiencia de configuración de alertas

Si es elegible para [las opciones de configuración de alertas agregadas](#licensing-for-alert-configuration-options), verá las siguientes opciones alineadas en la experiencia de creación de la Directiva de DLP.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Captura de pantalla que muestra opciones para los informes de incidentes para los usuarios que tienen derecho a opciones de configuración de alerta agregadas." border="false":::

Puede usar estas opciones de configuración de alerta para configurar una opción que defina la frecuencia con la que se puede producir una coincidencia de regla DLP antes de que se desencadene una alerta. Esta configuración le permite configurar una directiva para generar una alerta cada vez que una actividad coincida con las condiciones de la Directiva o cuando se supere un umbral determinado, en función del número de actividades o basadas en el volumen de datos exfiltrados.

Si es elegible para [las opciones de configuración de alertas de evento único](#licensing-for-alert-configuration-options), verá la siguiente opción de configuración de alerta en la experiencia de creación de directivas de DLP. Use esta opción para crear una alerta que se genera cada vez que se produce una coincidencia de regla DLP debido a una actividad de usuario.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Captura de pantalla que muestra opciones para los informes de incidentes para los usuarios que tienen derecho a opciones de configuración de alerta agregadas." border="false":::

## <a name="dlp-alert-management-dashboard"></a>Panel de administración de alertas de DLP

Para trabajar con el panel de administración de alertas de DLP:

1.  En el [centro de cumplimiento de Microsoft 365](https://www.compliance.microsoft.com), vaya a **prevención de pérdida de datos**.

2.  Seleccione la pestaña **alertas** para ver el panel alertas de DLP.

    -   Elija Filtros para refinar la lista de alertas. Elija **personalizar columnas** para mostrar las propiedades que desea ver. También puede elegir ordenar las alertas en orden ascendente o descendente en cualquier columna.
    -   Seleccione una alerta para ver los detalles:

        :::image type="content" source="../media/alert-details.png" alt-text="Captura de pantalla que muestra opciones para los informes de incidentes para los usuarios que tienen derecho a opciones de configuración de alerta agregadas." border="false":::

1.  Seleccione la ficha **eventos** para ver todos los eventos asociados a la alerta. Puede elegir un evento concreto para ver sus detalles.
    En la tabla siguiente se muestran algunos detalles del evento.
    
    | Categoría          | Nombre de propiedad                 | Descripción                                                                | Tipos de evento aplicables                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*Detalles del evento*||
    |      | Id                            | IDENTIFICADOR único asociado con el evento                                        | Todos los eventos                               |
    |                   | Ubicación                      | Carga de trabajo en la que se detectó el evento                                      | Todos los eventos                               |
    |                   | Tiempo de actividad              | Hora de la actividad del usuario que causó la infracción de DLP                    | Todos los eventos                               |
    |*Entidades afectadas*||
    |  | Usuario                          | Usuario que causó la infracción de DLP                                          | Todos los eventos                               |
    |                   | Nombre de host                      | Nombre de host del equipo en el que se detectó la infracción de DLP              | Eventos de dispositivos                           |
    |                   | Dirección IP                    | Dirección IP de la máquina                                                  | Eventos de dispositivos                           |
    |                   | Ruta de acceso de archivo                     | Ruta de acceso absoluta del archivo implicado en la infracción                        | Eventos de SharePoint, OneDrive y dispositivos |
    |                   | Destinatarios de correo electrónico              | Destinatarios del correo electrónico que infringió la Directiva DLP                       | Eventos de Exchange                          |
    |                   | Asunto de correo electrónico                 | Asunto del correo electrónico que infringió la Directiva DLP                          | Eventos de Exchange                          |
    |                   | Datos adjuntos de correo electrónico             | Nombres de los datos adjuntos en el correo electrónico que infringió la Directiva DLP         | Eventos de Exchange                          |
    |                   | Propietario del sitio                    | Nombre del propietario del sitio                                                     | Eventos de SharePoint y OneDrive           |
    |                   | Dirección URL del sitio                      | Dirección URL completa del sitio de SharePoint o de OneDrive                                | Eventos de SharePoint y OneDrive           |
    |                   | Archivo creado                  | Fecha y hora de creación del archivo                                                      | Eventos de SharePoint y OneDrive           |
    |                   | Fecha de última modificación del archivo            | Hora de la última modificación del archivo                                  | Eventos de SharePoint y OneDrive           |
    |                   | Tamaño de archivos                     | Tamaño del archivo                                                           | Eventos de SharePoint y OneDrive           |
    |                   | Propietario del archivo                    | Propietario del archivo                                                          | Eventos de SharePoint y OneDrive           |
    |*Detalles de la Directiva*||
    |     | Coincidencia de directiva DLP            | Nombre de la Directiva DLP que coincide                                    | Todos los eventos                               |
    |                   | Coincidencia de regla                  | Nombre de la regla DLP en la Directiva DLP que coincide                    | Todos los eventos                               |
    |                   | Tipos de información confidencial detectados | Tipos de información confidencial que se han detectado como parte de la Directiva DLP | Todos los eventos                               |
    |                   | Acciones realizadas                 | Acciones tomadas como parte de la Directiva de DLP coincidente                          | Todos los eventos                               |
    |                   | Directiva de overrode de usuario          | Si el usuario overrode la Directiva a través de la sugerencia de Directiva                | Todos los eventos                               |
    |                   | Invalidar texto de justificación   | Justificación proporcionada para invalidar la sugerencia de Directiva                          | Todos los eventos                               |
    
1.  Seleccione la ficha tipos de información **confidencial** para ver los detalles sobre los tipos de información confidencial detectados en el contenido. Entre los detalles se incluyen la confianza y el recuento.

2.  Una vez que haya investigado la alerta, elija **administrar alerta** para cambiar el estado (**activo**, en **investigación**, **desechado**o **resuelto**). También puede agregar comentarios y asignar la alerta a alguien de su organización.

    -   Para ver el historial de administración de flujos de trabajo, elija **registro de administración**.
    -   Después de realizar la acción necesaria para la alerta, establezca el estado de la alerta en **resuelto**.
