---
title: Compilación de consultas mediante el modo guiado en Microsoft 365 Defender búsqueda avanzada
description: Obtenga información sobre cómo crear consultas en modo guiado mediante la combinación de diferentes filtros y condiciones disponibles.
keywords: modo guiado, búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.openlocfilehash: b054bd3518d9cdc1bdbb4a11f59dfff70832b701
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68080181"
---
# <a name="build-hunting-queries-using-guided-mode-in-microsoft-365-defender"></a>Compilación de consultas de búsqueda mediante el modo guiado en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

El generador de consultas en modo guiado permite a los analistas crear consultas de búsqueda *significativas sin conocer Lenguaje de consulta Kusto (KQL) o el esquema de datos*. Los analistas de cada nivel de experiencia pueden usar el generador de consultas para filtrar los datos de los últimos 30 días para buscar amenazas, expandir las investigaciones de incidentes, realizar análisis de datos en datos de amenazas o centrarse en áreas de amenazas específicas.

El analista puede elegir qué conjunto de datos examinar y qué filtros y condiciones usar para restringir los datos a lo que necesitan. 


## <a name="open-query-in-builder"></a>Abrir consulta en el generador
En la página **Búsqueda avanzada** , seleccione **Crear nuevo** para abrir una nueva pestaña de consulta y seleccione **Consulta en el generador**. 

![Captura de pantalla del generador de consultas en modo guiado](../../media/guided-hunting/query-in-builder-page.png)

Esto le lleva al modo guiado, donde puede construir la consulta seleccionando diferentes componentes mediante menús desplegables.

## <a name="specify-the-data-domain-to-hunt-in"></a>Especificar el dominio de datos en el que se va a buscar
Para controlar el ámbito de la búsqueda, seleccione el dominio que abarca la consulta:

![Captura de pantalla de la lista desplegable de dominios del generador de consultas en modo guiado](../../media/guided-hunting/query-builder-view-in.png)


Al seleccionar **Todos se** incluyen datos de todos los dominios a los que actualmente tiene acceso. La reducción a un dominio específico permite filtros relevantes solo para ese dominio. 

Puede elegir entre:
- Todos los dominios: para examinar todos los datos disponibles en la consulta
- Puntos de conexión: para examinar los datos de los puntos de conexión según lo proporcionado por Microsoft Defender para punto de conexión
- Aplicaciones e identidades: para examinar los datos de aplicación e identidad proporcionados por Microsoft Defender for Cloud Apps y Microsoft Defender for Identity, los usuarios familiarizados con el [registro de actividad](/defender-cloud-apps/activity-filters) pueden encontrar los mismos datos aquí.
- Email y colaboración: para examinar los datos de aplicaciones de colaboración y correo electrónico, como SharePoint, OneDrive y otros, los usuarios familiarizados con [el Explorador de amenazas](/office-365-security/threat-explorer) pueden encontrar los mismos datos aquí.

## <a name="use-basic-filters"></a>Uso de filtros básicos

De forma predeterminada, la búsqueda guiada incluye algunos filtros básicos para empezar rápidamente. 

![Captura de pantalla del conjunto de filtros básicos del generador de consultas en modo guiado](../../media/guided-hunting/query-builder-basic-filters.png)



Al elegir un origen de datos, por ejemplo, **Puntos de conexión**, el generador de consultas muestra solo los grupos de filtros aplicables. A continuación, puede elegir un filtro que le interese restringir seleccionando ese grupo de filtros, por ejemplo, **EventType**, y seleccionando el filtro de su elección.

![Captura de pantalla del conjunto de filtros básicos del punto de conexión del generador de consultas en modo guiado](../../media/guided-hunting/query-builder-query-basic-filter.png)



Una vez que la consulta esté lista, seleccione el botón azul **Ejecutar consulta** . Si el botón está atenuado, significa que la consulta debe rellenarse o editarse aún más. 

>[!NOTE]
> La vista de filtro básica solo usa el operador **AND** , lo que significa que la ejecución de la consulta genera resultados para los que todos los filtros establecidos son true. 


## <a name="load-sample-queries"></a>Carga de consultas de ejemplo

Otra manera rápida de familiarizarse con la búsqueda guiada es cargar consultas de ejemplo mediante el menú desplegable **Cargar consultas de ejemplo** . 
![Captura de pantalla de la lista de consultas de ejemplo de carga del generador de consultas en modo guiado](../../media/guided-hunting/load-sample-queries.png)

>[!NOTE] 
> Al seleccionar una consulta de ejemplo, se invalida la consulta existente. 

Una vez cargada la consulta de ejemplo, seleccione **Ejecutar consulta**.

![Captura de pantalla de la consulta cargada del generador de consultas en modo guiado](../../media/guided-hunting/load-sample-queries-1.png)

Si ha seleccionado previamente un dominio, la lista de consultas de ejemplo disponibles cambia en consecuencia.

![Captura de pantalla de la lista restringida del generador de consultas en modo guiado](../../media/guided-hunting/load-sample-queries-2.png)

Para restaurar la lista completa de consultas de ejemplo, seleccione **Todos los dominios** y vuelva a abrir **Consultas de ejemplo de carga**.

Si la consulta de ejemplo cargada usa filtros fuera del conjunto de filtros básico, el botón de alternancia se atenua. Para volver al conjunto de filtros básico, seleccione **Borrar todo** y, a continuación, cambie **Todos los filtros**. 


## <a name="use-more-filters"></a>Uso de más filtros

Para ver más grupos de filtros y condiciones, seleccione **Alternar para ver más filtros y condiciones**.

![Captura de pantalla de la alternancia de más filtros del generador de consultas en modo guiado](../../media/guided-hunting/query-builder-view-in-endpoints.png)

Cuando el botón de alternancia **Todos los filtros** está activo, ahora puede usar toda la gama de filtros y condiciones en modo guiado.

![Captura de pantalla del generador de consultas en modo guiado de todos los filtros activos](../../media/guided-hunting/query-builder-all-filters.png)




### <a name="create-conditions"></a>Crear condiciones

Para especificar un conjunto de datos que se usarán en la consulta, seleccione **Seleccionar un filtro**. Explore las distintas secciones de filtro para encontrar lo que está disponible para usted.
 
![Captura de pantalla que muestra los distintos filtros que puede usar](../../media/guided-hunting/query-builder-filters.png)

Escriba los títulos de la sección en el cuadro de búsqueda de la parte superior de la lista para buscar el filtro. Las secciones que terminan en *la información* contienen filtros que proporcionan información sobre los distintos componentes que se pueden examinar y filtran los estados de las entidades. Las secciones que terminan en *eventos* contienen filtros que permiten buscar cualquier evento supervisado en la entidad. Por ejemplo, para buscar actividades que impliquen determinados dispositivos, puede usar los filtros de la sección **Eventos de dispositivo** .

>[!NOTE]
> Al elegir un filtro que no está en la lista de filtros básicos, se desactiva o se desactiva el botón de alternancia para volver a la vista de filtros básicos. Para restablecer la consulta o quitar los filtros existentes en la consulta actual, seleccione **Borrar todo**. Esto también reactiva la lista de filtros básicos.


A continuación, establezca la condición adecuada para filtrar aún más los datos seleccionándolo en el segundo menú desplegable y proporcionando entradas en el tercer menú desplegable si es necesario:

![Captura de pantalla que muestra las diferentes condiciones que puede usar](../../media/guided-hunting/query-builder-operators-equals.png)

Puede agregar más condiciones a la consulta mediante las condiciones **AND** y **OR** . AND devuelve resultados que cumplen todas las condiciones de la consulta, mientras que OR devuelve resultados que cumplen cualquiera de las condiciones de la consulta.  

![Captura de pantalla que muestra los operadores AND OR](../../media/guided-hunting/query-builder-operators.png)

El refinamiento de la consulta le permite examinar automáticamente registros voluminosos para generar una lista de resultados que ya están dirigidos a su necesidad específica de búsqueda de amenazas.

Para saber qué tipos de datos se admiten y otras funcionalidades de modo guiado para ayudarle a ajustar la consulta, lea [Refinar la consulta en modo guiado](advanced-hunting-query-builder-details.md).

## <a name="try-sample-query-walk-throughs"></a>Pruebe los tutoriales de consulta de ejemplo

Otra manera de familiarizarse con la búsqueda guiada es cargar consultas de ejemplo creadas previamente en modo guiado. 

En la sección **Introducción** de la página de búsqueda, hemos proporcionado tres ejemplos de consulta guiada que puede cargar. Los ejemplos de consulta contienen algunos de los filtros y entradas más comunes que normalmente necesitaría en la búsqueda. La carga de cualquiera de las tres consultas de ejemplo abre una visita guiada sobre cómo construiría la entrada mediante el modo guiado.

![Captura de pantalla de tutoriales de consulta de introducción al generador de consultas en modo guiado](../../media/guided-hunting/load-examples.png)

Siga las instrucciones de las burbujas de enseñanza azules para construir la consulta. Seleccione **Ejecutar consulta**.

## <a name="try-some-queries"></a>Prueba de algunas consultas

### <a name="hunt-for-successful-connections-to-specific-ip"></a>Búsqueda de conexiones correctas a una dirección IP específica
Para buscar comunicaciones de red correctas a una dirección IP específica, empiece a escribir "ip" para obtener los filtros sugeridos:

![Captura de pantalla de la búsqueda del generador de consultas en modo guiado para conexiones correctas al primer filtro ip específica](../../media/guided-hunting/query-builder-hunt-ip.png)

Para buscar eventos que impliquen una dirección IP específica donde la dirección IP sea el destino de la comunicación, seleccione `DestinationIPAddress` en la sección Eventos de dirección IP. A continuación, seleccione el operador **equals** . Escriba la dirección IP en el tercer menú desplegable y presione **Entrar**:

![Captura de pantalla de la búsqueda del generador de consultas en modo guiado para obtener conexiones correctas a una dirección IP específica](../../media/guided-hunting/query-builder-hunt-ip-2.png)

A continuación, para agregar una segunda condición que busque eventos de comunicación de red correctos, busque el filtro de un tipo de evento específico:

![Captura de pantalla de la búsqueda del generador de consultas en modo guiado para conexiones correctas a una dirección IP específica, segunda condición](../../media/guided-hunting/query-builder-hunt-ip-3.png)

El filtro **EventType** busca los diferentes tipos de eventos registrados. Es equivalente a la columna **ActionType** que existe en la mayoría de las tablas de búsqueda avanzada. Selecciónelo para elegir uno o varios tipos de eventos por los que filtrar. Para buscar eventos de comunicación de red correctos, expanda la sección **DeviceNetworkEvents** y elija `ConnectionSuccess`:

![Captura de pantalla de la búsqueda del generador de consultas en modo guiado para conexiones correctas a una tercera condición de IP específica](../../media/guided-hunting/query-builder-hunt-ip-4.png)

Por último, seleccione **Ejecutar consulta** para buscar todas las comunicaciones de red correctas a la dirección IP 52.168.117.170:

![Captura de pantalla de la búsqueda del generador de consultas en modo guiado para conexiones correctas a una vista de resultados de IP específica](../../media/guided-hunting/query-builder-hunt-ip-5.png)

### <a name="hunt-for-high-confidence-phish-or-spam-emails-delivered-to-inbox"></a>Búsqueda de correos electrónicos de alta confianza o correo no deseado enviados a la bandeja de entrada 

Para buscar todos los correos electrónicos de correo no deseado y de alta confianza que se entregaron a la carpeta de bandeja de entrada en el momento de la entrega, seleccione **Primero ConfidenceLevel** en eventos de Email, seleccione **igual** y elija **Alto** en **Phish** y **Spam** en la lista cerrada sugerida que admite la selección múltiple:

![Captura de pantalla del generador de consultas en modo guiado que busca correos electrónicos de alta confianza o correo no deseado entregados a la bandeja de entrada, primera condición](../../media/guided-hunting/hunt-phishing-1.png)

A continuación, agregue otra condición, esta vez especificando la carpeta o **DeliveryLocation, Bandeja de entrada o carpeta**. 

![Captura de pantalla del generador de consultas en modo guiado que busca correos electrónicos de alta confianza o correo no deseado entregados a la bandeja de entrada, segunda condición](../../media/guided-hunting/hunt-phishing-2.png)




## <a name="see-also"></a>Vea también

- [Refinar la consulta en modo guiado](advanced-hunting-query-builder-details.md)
- [Trabajar con resultados de consulta en modo guiado](advanced-hunting-query-builder-results.md)
 - [Entender el esquema](advanced-hunting-schema-tables.md)
