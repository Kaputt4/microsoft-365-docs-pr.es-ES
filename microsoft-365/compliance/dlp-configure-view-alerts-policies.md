---
title: Configurar y ver alertas para las directivas DLP (versión preliminar)
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
description: Obtenga información sobre cómo definir y administrar alertas para directivas DLP.
ms.openlocfilehash: addf46b27575f1a1cc062949aedb7ecdecaf7286
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651478"
---
# <a name="configure-and-view-alerts-for-dlp-polices-preview"></a>Configurar y ver alertas para directivas DLP (versión preliminar)

En este artículo se muestra cómo definir directivas de alerta enriquecciones vinculadas a las directivas de prevención de pérdida de datos (DLP). Verá cómo usar el nuevo panel de administración de alertas DLP en el Centro de cumplimiento de [Microsoft 365](https://compliance.microsoft.com/) para ver alertas, eventos y metadatos asociados para infracciones de directivas DLP.

## <a name="features"></a>Características

Las siguientes características forman parte de esta versión preliminar:

-   **Panel de administración de alertas DLP:** en el Centro de cumplimiento de [Microsoft 365,](https://compliance.microsoft.com/)este panel muestra alertas para las directivas DLP que se aplican en las siguientes cargas de trabajo:

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   Dispositivos
-   **Opciones avanzadas de configuración de alertas:** estas opciones forman parte del flujo de creación de directivas DLP. Úsenlos para crear configuraciones de alerta enriquecciones. Puede crear una alerta de evento único o una alerta agregada, según el número de eventos o el tamaño de los datos filtrados.

## <a name="before-you-begin"></a>Antes de empezar

Antes de empezar, asegúrese de que tiene los requisitos previos necesarios:

-   Licencias para el panel de administración de alertas de DLP
-   Licencias para opciones de configuración de alertas
-   Roles

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Licencias para el panel de administración de alertas dlp

Todos los inquilinos elegibles para DLP de Office 365 pueden acceder al nuevo panel de administración de alertas dlp. To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business. Para obtener más información acerca de los requisitos de licencia para DLP de Office 365, vea ¿Qué licencias proporcionan los derechos para que un usuario se beneficie [del servicio?](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)

Los clientes que participan en la versión preliminar pública de [DLP](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide) de punto de conexión o que son aptos para DLP de Teams verán sus alertas de directiva [DLP](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams?view=o365-worldwide) de punto de conexión y alertas de directiva DLP de Teams en el panel de administración de alertas dlp.

### <a name="licensing-for-alert-configuration-options"></a>Licencias para opciones de configuración de alertas

-   Configuración de alerta de evento **único:** las organizaciones que tienen una suscripción E1, F1 o G1 o una suscripción E3 o G3 pueden crear directivas de alerta solo cuando se desencadena una alerta cada vez que se produce una actividad.
-   **Configuración de alerta agregada:** para configurar directivas de alerta agregadas basadas en un umbral, debe tener una de las siguientes configuraciones:
    -   Una suscripción E5 o G5
    -   Una suscripción E1, F1 o G1 o una suscripción E3 o G3 que incluya una de las siguientes características:
        -   Protección contra amenazas avanzada de Office 365 (plan 2)
        -   Cumplimiento de Microsoft 365 E5
        -   Licencia de complemento de auditoría y exhibición de documentos electrónicos de Microsoft 365

### <a name="roles"></a>Roles

Si desea ver el panel de administración de alertas dlp o editar las opciones de configuración de alertas en una directiva DLP, debe ser miembro de uno de estos grupos de roles:

-   Administrador de cumplimiento
-   Administrador de datos de cumplimiento
-   Administrador de seguridad
-   Operador de seguridad
-   Lector de seguridad

Para obtener acceso al panel de administración de alertas de DLP, necesita la función Administrar alertas y cualquiera de las siguientes funciones:

-   Administración de cumplimiento de DLP
-   View-Only de cumplimiento de DLP

## <a name="alert-configuration-experience"></a>Experiencia de configuración de alertas

Si cumple los requisitos para [las](#licensing-for-alert-configuration-options)opciones de configuración de alerta agregadas, verá las siguientes opciones en línea en la experiencia de creación de directivas DLP.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Captura de pantalla que muestra las opciones de informes de incidentes para los usuarios que son aptos para opciones de configuración de alerta agregadas." border="false":::

Puede usar estas opciones de configuración de alertas para configurar una configuración que defina la frecuencia con la que puede producirse una coincidencia de regla DLP antes de que se desencadene una alerta. Esta configuración permite configurar una directiva para generar una alerta cada vez que una actividad coincide con las condiciones de la directiva o cuando se supera un umbral determinado, en función del número de actividades o en función del volumen de datos exfiltrados.

Si cumple los requisitos para las [opciones](#licensing-for-alert-configuration-options)de configuración de alerta de un solo evento, verá la siguiente opción de configuración de alertas en la experiencia de creación de directivas DLP. Use esta opción para crear una alerta que se genera cada vez que se produce una coincidencia de regla DLP debido a una actividad de usuario.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Captura de pantalla que muestra las opciones para los informes de incidentes para los usuarios que son aptos para las opciones de configuración de alertas de un solo evento." border="false":::

## <a name="dlp-alert-management-dashboard"></a>Panel de administración de alertas dlp

Para trabajar con el panel de administración de alertas dlp:

1.  En el [Centro de cumplimiento de Microsoft 365,](https://www.compliance.microsoft.com)vaya a Prevención de pérdida de **datos.**

2.  Seleccione la **pestaña Alertas** para ver el panel de alertas de DLP.

    -   Elija filtros para refinar la lista de alertas. Elija **Personalizar columnas** para enumerar las propiedades que desea ver. También puedes ordenar las alertas en orden ascendente o descendente en cualquier columna.
    -   Seleccione una alerta para ver los detalles:

        :::image type="content" source="../media/alert-details.png" alt-text="Captura de pantalla que muestra detalles de alertas en el panel de administración de alertas dlp." border="false":::

1.  Seleccione la **pestaña** Eventos para ver todos los eventos asociados con la alerta. Puedes elegir un evento determinado para ver sus detalles.
    En la tabla siguiente se muestran algunos de los detalles del evento.
    
    | Categoría          | Nombre de propiedad                 | Descripción                                                                | Tipos de eventos aplicables                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*Detalles del evento*||
    |      | Id                            | Identificador único asociado al evento                                        | Todos los eventos                               |
    |                   | Ubicación                      | Carga de trabajo en la que se detectó el evento                                      | Todos los eventos                               |
    |                   | Hora de actividad              | Hora de la actividad del usuario que provocó la infracción de DLP                    | Todos los eventos                               |
    |*Entidades afectadas*||
    |  | User                          | Usuario que causó la infracción de DLP                                          | Todos los eventos                               |
    |                   | Nombre de host                      | Nombre de host de la máquina donde se detectó la infracción de DLP              | Eventos de dispositivos                           |
    |                   | Dirección IP                    | Dirección IP del equipo                                                  | Eventos de dispositivos                           |
    |                   | Ruta de acceso de archivo                     | Ruta absoluta del archivo implicado en la infracción                        | Eventos de SharePoint, OneDrive y Dispositivos |
    |                   | Destinatarios de correo electrónico              | Destinatarios del correo electrónico que infringió la directiva DLP                       | Eventos de Exchange                          |
    |                   | Asunto del correo electrónico                 | Asunto del correo electrónico que infringió la directiva DLP                          | Eventos de Exchange                          |
    |                   | Datos adjuntos de correo electrónico             | Nombres de los datos adjuntos del correo electrónico que infringió la directiva DLP         | Eventos de Exchange                          |
    |                   | Propietario del sitio                    | Nombre del propietario del sitio                                                     | Eventos de SharePoint y OneDrive           |
    |                   | Dirección URL del sitio                      | Dirección URL completa del sitio de SharePoint o OneDrive                                | Eventos de SharePoint y OneDrive           |
    |                   | Archivo creado                  | Hora de creación de archivos                                                      | Eventos de SharePoint y OneDrive           |
    |                   | Archivo modificado por última vez            | Hora de la última modificación del archivo                                  | Eventos de SharePoint y OneDrive           |
    |                   | Tamaño de archivos                     | Tamaño del archivo                                                           | Eventos de SharePoint y OneDrive           |
    |                   | Propietario del archivo                    | Propietario del archivo                                                          | Eventos de SharePoint y OneDrive           |
    |*Detalles de la directiva*||
    |     | Directiva DLP coincidente            | Nombre de la directiva DLP coincidente                                    | Todos los eventos                               |
    |                   | Regla coincidente                  | Nombre de la regla DLP en la directiva DLP coincidente                    | Todos los eventos                               |
    |                   | Tipos de información confidencial detectados | Tipos de información confidencial detectados como parte de la directiva DLP | Todos los eventos                               |
    |                   | Acciones realizadas                 | Acciones realizadas como parte de la directiva DLP coincidente                          | Todos los eventos                               |
    |                   | Directiva de exceso de usuarios          | Si el usuario ha sobresalto la directiva a través de la sugerencia de directiva                | Todos los eventos                               |
    |                   | Invalidar texto de justificación   | Justificación proporcionada para invalidar la sugerencia de directiva                          | Todos los eventos                               |
    
1.  Seleccione la **pestaña Tipos de información** confidencial para ver detalles sobre los tipos de información confidencial detectados en el contenido. Los detalles incluyen la confianza y el recuento.

2.  Después de investigar la alerta, elija Administrar **alerta** para cambiar el estado **(Activo,** **Investigando,** **Descartado** o **Resuelto).** También puede agregar comentarios y asignar la alerta a alguien de su organización.

    -   Para ver el historial de administración de flujos de trabajo, elija **Registro de administración.**
    -   Después de realizar la acción necesaria para la alerta, establezca el estado de la alerta en **Resuelto.**
