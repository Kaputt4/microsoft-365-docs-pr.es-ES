---
title: Configuración y visualización de alertas para directivas DLP
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
description: Obtenga información sobre cómo definir y administrar alertas para directivas de prevención de pérdida de datos.
ms.openlocfilehash: 60d5188b9288b1e131e36e145f7abb98a34d5ead
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66627655"
---
# <a name="configure-and-view-alerts-for-data-loss-prevention-polices"></a>Configuración y visualización de alertas para las directivas de prevención de pérdida de datos

las directivas de Prevención de pérdida de datos de Microsoft Purview (DLP) pueden tomar medidas de protección para evitar el uso compartido involuntario de elementos confidenciales. Cuando se realiza una acción en un elemento confidencial, se le puede notificar mediante la configuración de alertas para DLP. En este artículo se muestra cómo definir directivas de alerta enriquecidas vinculadas a las directivas de prevención de pérdida de datos (DLP). Verá cómo usar el nuevo panel de administración de alertas DLP en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a> para ver alertas, eventos y metadatos asociados para infracciones de directiva DLP.

## <a name="features"></a>Características

Las siguientes características forman parte de esto:

-   **Panel de administración de alertas DLP**: en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a>, este panel muestra alertas de directivas DLP que se aplican en las siguientes cargas de trabajo:

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   Dispositivos
-   **Opciones avanzadas de configuración de alertas**: estas opciones forman parte del flujo de creación de directivas DLP. Úselas para crear configuraciones de alerta enriquecidas. Puede crear una alerta de evento único o una alerta agregada, en función del número de eventos o del tamaño de los datos filtrados.

## <a name="before-you-begin"></a>Antes de empezar

Antes de empezar, asegúrese de que tiene los requisitos previos necesarios:

-   Licencias para el panel de administración de alertas DLP
-   Licencias para opciones de configuración de alertas
-   Funciones

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Licencias para el panel de administración de alertas DLP

Todos los inquilinos aptos para Office 365 DLP pueden acceder al nuevo panel de administración de alertas DLP. Para empezar, debe ser apto para Office 365 DLP para Exchange Online, SharePoint Online y OneDrive para la Empresa. Para obtener más información sobre los requisitos de licencia para Office 365 DLP, vea [¿Qué licencias proporcionan los derechos para que un usuario se beneficie del servicio?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).

Los clientes que usan [DLP de punto de conexión](endpoint-dlp-learn-about.md) que son aptos para DLP de [Teams](dlp-microsoft-teams.md) verán sus alertas de directiva DLP de punto de conexión y las alertas de directiva DLP de Teams en el panel de administración de alertas DLP.

### <a name="licensing-for-alert-configuration-options"></a>Licencias para opciones de configuración de alertas

- **Configuración de alertas de evento único**: las organizaciones que tienen una suscripción E1, F1 o G1 o una suscripción E3 o G3 solo pueden crear directivas de alertas cuando se desencadena una alerta cada vez que se produce una actividad.
- **Configuración de alerta agregada**: para configurar directivas de alerta agregadas basadas en un umbral, debe tener cualquiera de las siguientes configuraciones:
  - Una suscripción A5 o G5
  - Una suscripción E1, F1 o G1 o una suscripción E3 o G3 que incluya una de las siguientes características:
    - Protección contra amenazas avanzada de Office 365 (plan 2)
    - Cumplimiento de Microsoft 365 E5
    - Licencia de complemento de auditoría y exhibición de documentos electrónicos de Microsoft 365

### <a name="roles"></a>Funciones

Si desea ver el panel de administración de alertas DLP o editar las opciones de configuración de alertas en una directiva DLP, debe ser miembro de uno de estos grupos de roles:

-   Administrador de cumplimiento
-   Administrador de datos de cumplimiento
-   Administrador de seguridad
-   Operador de seguridad
-   Lector de seguridad

Para acceder al panel de administración de alertas DLP, necesita el rol Administrar alertas y cualquiera de los siguientes roles:

-   Administración de cumplimiento de DLP
-   View-Only administración de cumplimiento de DLP

## <a name="alert-configuration-experience"></a>Experiencia de configuración de alertas

Si es apto para [las opciones de configuración de alertas agregadas](#licensing-for-alert-configuration-options), verá las siguientes opciones insertadas en la experiencia de creación de directivas DLP.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Captura de pantalla que muestra las opciones de informes de incidentes para los usuarios que son aptos para las opciones de configuración de alerta agregada." border="false":::

Esta configuración le permite configurar una directiva para generar una alerta:

- cada vez que una actividad coincide con las condiciones de la directiva
- cuando se cumple o se supera el umbral definido
- en función del número de actividades
- basado en el volumen de datos filtrados

Para evitar una avalancha de correos electrónicos de notificación, todas las coincidencias que se producen en un período de tiempo de un minuto y son para la misma regla DLP y en la misma ubicación se agrupan en la misma alerta. La característica de período de tiempo de agregación de un minuto está disponible en: 

- Una suscripción A5 o G5
- Una suscripción E1, F1 o G1 o una suscripción E3 o G3 que incluya una de las siguientes características:
    - Protección contra amenazas avanzada de Office 365 (plan 2)
    - Cumplimiento de Microsoft 365 E5
    - Licencia de complemento de auditoría y exhibición de documentos electrónicos de Microsoft 365
 
Para las organizaciones que tienen una suscripción E1, F1 o G1 o una suscripción E3 o G3, el período de tiempo de agregación es de 15 minutos.

## <a name="dlp-alert-management-dashboard"></a>Panel de administración de alertas DLP

Para trabajar con el panel de administración de alertas DLP:

1.  En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a>, vaya a **Prevención de pérdida de datos**.

2.  Seleccione la pestaña **Alertas** para ver el panel de alertas DLP.

    -   Elija filtros para refinar la lista de alertas. Elija **Personalizar columnas** para mostrar las propiedades que desea ver. También puede optar por ordenar las alertas en orden ascendente o descendente en cualquier columna.
    -   Seleccione una alerta para ver los detalles:

        :::image type="content" source="../media/alert-details.png" alt-text="Captura de pantalla que muestra los detalles de la alerta en el panel de administración de alertas DLP." border="false":::

1.  Seleccione la pestaña **Eventos** para ver todos los eventos asociados a la alerta. Puede elegir un evento determinado para ver sus detalles. En la tabla siguiente se muestran algunos de los detalles del evento.
    
    | Categoría          | Nombre de propiedad                 | Descripción                                                                | Tipos de eventos aplicables                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*Detalles del evento*||
    |      | Id                            | Identificador único asociado al evento                                        | Todos los eventos                               |
    |                   | Ubicación                      | Carga de trabajo donde se detectó el evento                                      | Todos los eventos                               |
    |                   | Tiempo de actividad              | Hora de la actividad del usuario que provocó la infracción de DLP                    | Todos los eventos                               |
    |*Entidades afectadas*||
    |  | Usuario                          | Usuario que provocó la infracción de DLP                                          | Todos los eventos                               |
    |                   | Nombre de host                      | Nombre de host de la máquina donde se detectó la infracción de DLP              | Eventos de dispositivos                           |
    |                   | Dirección IP                    | Dirección IP de la máquina                                                  | Eventos de dispositivos                           |
    |                   | Ruta de acceso de archivo                     | Ruta de acceso absoluta del archivo implicado en la infracción                        | Eventos de SharePoint, OneDrive y Dispositivos |
    |                   | Destinatarios de correo electrónico              | Destinatarios del correo electrónico que infringió la directiva DLP                       | Eventos de Exchange                          |
    |                   | Asunto del correo electrónico                 | Asunto del correo electrónico que infringió la directiva DLP                          | Eventos de Exchange                          |
    |                   | Datos adjuntos de correo electrónico             | Nombres de los datos adjuntos en el correo electrónico que infringió la directiva DLP         | Eventos de Exchange                          |
    |                   | Propietario del sitio                    | Nombre del propietario del sitio                                                     | Eventos de SharePoint y OneDrive           |
    |                   | Dirección URL del sitio                      | Dirección URL completa del sitio de SharePoint o OneDrive                                | Eventos de SharePoint y OneDrive           |
    |                   | Archivo creado                  | Hora de creación de archivos                                                      | Eventos de SharePoint y OneDrive           |
    |                   | Archivo modificado por última vez            | Hora de la última modificación del archivo                                  | Eventos de SharePoint y OneDrive           |
    |                   | Tamaño de archivos                     | Tamaño del archivo                                                           | Eventos de SharePoint y OneDrive           |
    |                   | Propietario del archivo                    | Propietario del archivo                                                          | Eventos de SharePoint y OneDrive           |
    |*Detalles de la directiva*||
    |     | Directiva DLP coincidente            | Nombre de la directiva DLP coincidente                                    | Todos los eventos                               |
    |                   | Regla coincidente                  | Nombre de la regla DLP en la directiva DLP coincidente                    | Todos los eventos                               |
    |                   | Tipos de información confidencial detectados | Tipos de información confidencial que se detectaron como parte de la directiva DLP | Todos los eventos                               |
    |                   | Acciones realizadas                 | Acciones realizadas como parte de la directiva DLP coincidente                          | Todos los eventos                               |
    |                   | Directiva de superada por el usuario          | Si el usuario superó la directiva a través de la sugerencia de directiva                | Todos los eventos                               |
    |                   | Invalidar texto de justificación   | Justificación proporcionada para invalidar la sugerencia de directiva                          | Todos los eventos                               |
    
1.  Seleccione la pestaña **Tipos de información confidencial** para ver detalles sobre los tipos de información confidencial detectados en el contenido. Los detalles incluyen la confianza y el recuento.

2.  Después de investigar la alerta, elija **Administrar alerta** para cambiar el estado (**Activo**, **Investigar**, **Descartado** o **Resuelto**). También puede agregar comentarios y asignar la alerta a alguien de su organización.

    -   Para ver el historial de la administración de flujos de trabajo, elija **Registro de administración**.
    -   Después de realizar la acción necesaria para la alerta, establezca el estado de la alerta en **Resuelto**.
