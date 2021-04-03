---
title: Crear reglas de detección personalizadas en ATP de Microsoft Defender
ms.reviewer: ''
description: Obtenga información sobre cómo crear reglas de detección personalizadas basadas en consultas avanzadas de búsqueda
keywords: detecciones personalizadas, crear, administrar, alertas, editar, ejecutar a petición, frecuencia, intervalo, reglas de detección, búsqueda avanzada, búsqueda, consulta, acciones de respuesta, mdatp, atp de microsoft defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 15dec5396a5ba95fe3ec7af5f9a72bbf15e07140
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500496"
---
# <a name="create-custom-detection-rules"></a>Crear reglas de detección personalizadas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Las reglas de [](advanced-hunting-overview.md) detección personalizadas creadas a partir de consultas avanzadas de búsqueda permiten supervisar proactivamente varios eventos y estados del sistema, incluidos la actividad de infracciones sospechosas y dispositivos mal configurados. Puede configurarlos para que se ejecuten a intervalos regulares, generando alertas y llevando a cabo acciones de respuesta siempre que haya coincidencias.

Lea este artículo para obtener información sobre cómo crear nuevas reglas de detección personalizadas. O [vea ver y administrar reglas existentes.](custom-detections-manage.md)

> [!NOTE]
> Para crear o administrar detecciones personalizadas, [el rol](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) debe tener el permiso administrar la **configuración de** seguridad.

## <a name="1-prepare-the-query"></a>1. Prepare la consulta.

En el Centro de seguridad de Microsoft Defender, vaya a **Búsqueda avanzada** y seleccione una consulta existente o cree una nueva consulta. Al usar una nueva consulta, ejecute la consulta para identificar errores y comprender los posibles resultados.

>[!IMPORTANT]
>Para evitar que el servicio devuelva demasiadas alertas, cada regla se limita a generar solo 100 alertas cada vez que se ejecuta. Antes de crear una regla, ajusta la consulta para evitar alertas de actividad normal del día a día.

### <a name="required-columns-in-the-query-results"></a>Columnas necesarias en los resultados de la consulta

Para usar una consulta para una regla de detección personalizada, la consulta debe devolver las siguientes columnas:

- `Timestamp`
- `DeviceId`
- `ReportId`

Las consultas simples, como las que no usan el operador or para personalizar o agregar resultados, normalmente `project` `summarize` devuelven estas columnas comunes.

Hay varias maneras de garantizar que las consultas más complejas devuelvan estas columnas. Por ejemplo, si prefieres agregar y contar por , aún puedes devolverlos y obtenerlos del evento más reciente que implica `DeviceId` `Timestamp` cada `ReportId` dispositivo.

La consulta de ejemplo siguiente cuenta el número de dispositivos únicos ( ) con detecciones antivirus y lo usa para buscar solo aquellos dispositivos con más `DeviceId` de cinco detecciones. Para devolver el último `Timestamp` y el correspondiente , usa el operador con la `ReportId` `summarize` `arg_max` función.

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> Para obtener un mejor rendimiento de consulta, establezca un filtro de tiempo que coincida con la frecuencia de ejecución prevista para la regla. Dado que la ejecución menos frecuente es cada 24 horas, el filtrado del último día cubrirá todos los datos nuevos.

## <a name="2-create-a-new-rule-and-provide-alert-details"></a>2. Cree una nueva regla y proporcione detalles de alerta.

Con la consulta en el editor de consultas, seleccione **Crear regla de detección** y especifique los siguientes detalles de alerta:

- **Nombre de detección**: nombre de la regla de detección
- **Frecuencia:** intervalo para ejecutar la consulta y realizar acciones. [Vea instrucciones adicionales a continuación](#rule-frequency)
- **Título de alerta:** título que se muestra con alertas desencadenadas por la regla
- **Gravedad:** riesgo potencial del componente o actividad identificado por la regla. [Leer sobre gravedades de alerta](alerts-queue.md#severity)
- **Categoría**: tipo de componente o actividad de amenaza, si la hay. [Leer sobre categorías de alertas](alerts-queue.md#understanding-alert-categories)
- **MITRE ATT&técnicas de CK:** una o más técnicas de ataque identificadas por la regla como se documentan en el marco&CK de MITRE ATT. Esta sección no está disponible con determinadas categorías de alertas, como malware, ransomware, actividad sospechosa y software no deseado
- **Descripción:** más información sobre el componente o la actividad identificada por la regla 
- **Acciones recomendadas:** acciones adicionales que los respondedores pueden realizar en respuesta a una alerta

Para obtener más información acerca de cómo se muestran los detalles de alerta, [lea acerca de la cola de alertas](alerts-queue.md).

### <a name="rule-frequency"></a>Frecuencia de regla

Cuando se guarda, una nueva regla de detección personalizada se ejecuta inmediatamente y comprueba las coincidencias de los últimos 30 días de datos. A continuación, la regla se ejecuta de nuevo a intervalos fijos y duraciones de devolución según la frecuencia que elija:

- **Cada 24 horas:** se ejecuta cada 24 horas, comprobando los datos de los últimos 30 días
- **Cada 12 horas:** se ejecuta cada 12 horas, comprobando los datos de las últimas 24 horas
- **Cada 3 horas:** se ejecuta cada 3 horas, comprobando los datos de las últimas 6 horas
- **Cada hora:** se ejecuta cada hora, comprobando los datos de las últimas 2 horas

Al editar una regla, se ejecutará con los cambios aplicados en la siguiente hora de ejecución programada según la frecuencia que establezca.


> [!TIP]
> Coincide con los filtros de tiempo de la consulta con la duración de la devolución. Se omiten los resultados fuera de la duración de la devolución.

Seleccione la frecuencia que coincida con la frecuencia con la que desea supervisar las detecciones y tenga en cuenta la capacidad de su organización para responder a las alertas.

## <a name="3-choose-the-impacted-entities"></a>3. Elija las entidades afectadas.

Identifique las columnas de los resultados de la consulta en las que espera encontrar la entidad principal afectada o afectada. Por ejemplo, una consulta puede devolver los id. de dispositivo y de usuario. La identificación de cuál de estas columnas representa la entidad afectada principal ayuda al servicio a agregar alertas relevantes, correlacionar incidentes y acciones de respuesta de destino.

Solo puede seleccionar una columna para cada tipo de entidad. Las columnas que la consulta no devuelve no se pueden seleccionar.

## <a name="4-specify-actions"></a>4. Especifique acciones.

La regla de detección personalizada puede realizar automáticamente acciones en archivos o dispositivos devueltos por la consulta.

### <a name="actions-on-devices"></a>Acciones en dispositivos

Estas acciones se aplican a los dispositivos de la `DeviceId` columna de los resultados de la consulta:

- **Aislar dispositivo:** aplica aislamiento de red completo, lo que impide que el dispositivo se conecte a cualquier aplicación o servicio, excepto para el servicio Defender for Endpoint. [Más información sobre el aislamiento de dispositivos](respond-machine-alerts.md#isolate-devices-from-the-network)
- **Recopilar paquete de investigación:** recopila información del dispositivo en un archivo ZIP. [Más información sobre el paquete de investigación](respond-machine-alerts.md#collect-investigation-package-from-devices)
- **Ejecutar examen antivirus:** realiza un examen completo de Antivirus de Microsoft Defender en el dispositivo
- **Iniciar investigación:** inicia una [investigación automatizada](automated-investigations.md) en el dispositivo
- **Restringir la ejecución de** la aplicación: establece restricciones en el dispositivo para permitir que solo se ejecuten los archivos que están firmados con un certificado emitido por Microsoft. [Más información sobre cómo restringir la ejecución de aplicaciones](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a>Acciones en archivos

Estas acciones se aplican a los archivos de la `SHA1` columna o de los `InitiatingProcessSHA1` resultados de la consulta:

- **Allow/Block:** agrega automáticamente el archivo a la lista de [indicadores](manage-indicators.md) personalizados para que siempre pueda ejecutarse o bloquearse para que no se ejecute. Puedes establecer el ámbito de esta acción de modo que solo se haya realizado en grupos de dispositivos seleccionados. Este ámbito es independiente del ámbito de la regla.
- **Archivo de** cuarentena: elimina el archivo de su ubicación actual y coloca una copia en cuarentena

### <a name="actions-on-users"></a>Acciones en usuarios

- **Marcar usuario como comprometido:** establece el nivel de riesgo del usuario en "alto" en Azure Active Directory, desencadenando las directivas de protección de [identidades correspondientes.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)

## <a name="5-set-the-rule-scope"></a>5. Establezca el ámbito de regla.

Establezca el ámbito para especificar los dispositivos cubiertos por la regla:

- Todos los dispositivos
- Grupos de dispositivos específicos

Solo se consultarán los datos de dispositivos en el ámbito. Además, las acciones solo se realizarán en esos dispositivos.

## <a name="6-review-and-turn-on-the-rule"></a>6. Revise y active la regla.

Después de revisar la regla, seleccione **Crear** para guardarla. La regla de detección personalizada se ejecuta inmediatamente. Se ejecuta de nuevo en función de la frecuencia configurada para buscar coincidencias, generar alertas y realizar acciones de respuesta.

Puede ver [y administrar reglas de detección personalizadas,](custom-detections-manage.md)comprobar sus ejecuciones anteriores y revisar las alertas que han desencadenado. También puede ejecutar una regla a petición y modificarla.

## <a name="related-topics"></a>Temas relacionados

- [Ver y administrar reglas de detección personalizadas](custom-detections-manage.md)
- [Introducción a las detecciones personalizadas](overview-custom-detections.md)
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Conozca el lenguaje de consulta de búsqueda avanzada](advanced-hunting-query-language.md)
- [Ver y organizar alertas](alerts-queue.md)
