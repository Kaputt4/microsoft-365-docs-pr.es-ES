---
title: Creación y administración de reglas de detección personalizadas en Microsoft 365 defender
description: Obtenga información sobre cómo crear y administrar reglas de detección personalizadas basadas en consultas de búsqueda avanzada.
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, detecciones personalizadas, reglas, esquema, kusto, Microsoft 365, protección contra amenazas de Microsoft, RBAC, permisos, Microsoft defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 5de4532a1bba809cde16ba6033ab30773a832176
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846777"
---
# <a name="create-and-manage-custom-detections-rules"></a>Creación y administración de reglas de detecciones personalizadas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 defender

Las reglas de detección personalizadas son reglas que se pueden diseñar y ajustar mediante consultas de [búsqueda avanzada](advanced-hunting-overview.md) . Estas reglas permiten supervisar de forma proactiva varios eventos y Estados del sistema, como la actividad de infracciones y los extremos configurados incorrectamente. Puede establecer que se ejecuten a intervalos regulares, generando alertas y realizando acciones de respuesta siempre que haya coincidencias.

## <a name="required-permissions-for-managing-custom-detections"></a>Permisos necesarios para administrar detecciones personalizadas

Para administrar las detecciones personalizadas, debe tener asignado uno de estos roles:

- **Administrador de seguridad** : los usuarios con este [rol de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) pueden administrar la configuración de seguridad en el centro de seguridad de Microsoft 365 y en otros portales y servicios.

- **Operador de seguridad** : los usuarios con este [rol de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) pueden administrar alertas y tener acceso global de solo lectura a características relacionadas con la seguridad, incluida toda la información del centro de seguridad de Microsoft 365. Este rol es suficiente para administrar detecciones personalizadas sólo si el control de acceso basado en roles (RBAC) está desactivado en Microsoft defender para el punto de conexión. Si tiene configurado un RBAC, también necesitará el permiso **administrar la configuración de seguridad** de defender para el punto de conexión.

Para administrar los permisos necesarios, un **administrador global** puede:

- Asigne el rol de **Administrador** de seguridad o **operador de seguridad** en el centro de administración de [Microsoft 365](https://admin.microsoft.com/) en **funciones**  >  **Administrador de seguridad**.
- Compruebe la configuración de RBAC de Microsoft defender para extremo en el [centro de seguridad de Microsoft defender](https://securitycenter.windows.com/) en **configuración**  >  **Permissions**  >  **roles** de permisos. Seleccione el rol correspondiente para asignar el permiso **administrar la configuración de seguridad** .

> [!NOTE]
> Para administrar las detecciones personalizadas, los **operadores de seguridad** necesitarán el permiso administrar la **configuración de seguridad** en Microsoft defender para el punto de conexión si RBAC está activado.

## <a name="create-a-custom-detection-rule"></a>Crear una regla de detección personalizada
### <a name="1-prepare-the-query"></a>1. Prepare la consulta.

En el centro de seguridad de Microsoft 365, vaya a **búsqueda avanzada** y seleccione una consulta existente o cree una nueva consulta. Cuando use una consulta nueva, ejecute la consulta para identificar los errores y comprender los posibles resultados.

>[!IMPORTANT]
>Para evitar que el servicio devuelva demasiadas alertas, cada regla se limita a generar sólo 100 alertas cada vez que se ejecuta. Antes de crear una regla, ajuste su consulta para evitar alertas por actividades normales y cotidianas.


#### <a name="required-columns-in-the-query-results"></a>Columnas necesarias en los resultados de la consulta
Para crear una regla de detección personalizada, la consulta debe devolver las siguientes columnas:

- `Timestamp`: se usa para establecer la marca de hora para las alertas generadas
- `ReportId`— habilita las búsquedas para los registros originales
- Una de las siguientes columnas que identifican dispositivos, usuarios o buzones específicos:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (remitente del sobre o dirección de Return-Path)
    - `SenderMailFromAddress` (dirección del remitente mostrada por el cliente de correo electrónico)
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>Se agregará compatibilidad con entidades adicionales a medida que se agreguen nuevas tablas al [esquema de búsqueda avanzada](advanced-hunting-schema-tables.md).

Las consultas sencillas, como las que no usan el `project` `summarize` operador OR para personalizar o agregar resultados, normalmente devuelven estas columnas comunes.

Hay varias formas de garantizar que las consultas más complejas devuelven estas columnas. Por ejemplo, si prefiere agregar y contar por entidad en una columna como `DeviceId` , puede seguir devolviendo `Timestamp` y `ReportId` obtenerlo del evento más reciente que implique a cada uno de los únicos `DeviceId` .

La consulta de ejemplo siguiente cuenta el número de dispositivos únicos ( `DeviceId` ) con detecciones de antivirus y usa este recuento para buscar solo los dispositivos con más de cinco detecciones. Para devolver la última `Timestamp` y la correspondiente `ReportId` , se utiliza el `summarize` operador con la `arg_max` función.

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> Para mejorar el rendimiento de las consultas, establezca un filtro de tiempo que coincida con la frecuencia de ejecución prevista para la regla. Dado que la ejecución menos frecuente es _cada 24 horas_ , el filtrado del día pasado cubrirá todos los datos nuevos.

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. cree una nueva regla y proporcione los detalles de la alerta.

Con la consulta en el editor de consultas, seleccione **crear regla de detección** y especifique los siguientes detalles de alerta:

- **Nombre de detección** : nombre de la regla de detección
- **Frecuencia** : intervalo para ejecutar la consulta y realizar una acción. [Consulte más información a continuación](#rule-frequency)
- **Título** de la alerta: título que se muestra con alertas desencadenadas por la regla
- **Gravedad** : riesgo potencial del componente o actividad identificados por la regla
- **Categoría** : componente de amenaza o actividad identificada por la regla
- **Mitre att&CK** : una o varias técnicas de ataque identificadas por la regla según se documenta en el [marco de MITRE de ATT&CK](https://attack.mitre.org/). Esta sección está oculta para determinadas categorías de alertas, incluidos malware, ransomware, actividades sospechosas y software no deseado.
- **Descripción** : más información sobre el componente o la actividad identificados por la regla 
- **Acciones recomendadas** : acciones adicionales que los respondedores pueden llevar a cabo en respuesta a una alerta

#### <a name="rule-frequency"></a>Frecuencia de la regla
Al guardar o editar una nueva regla, se ejecuta y comprueba si hay coincidencias de los últimos 30 días de datos. A continuación, la regla se ejecuta de nuevo a intervalos fijos, aplicando una duración de lookback basada en la frecuencia elegida:

- **Cada 24 horas** : se ejecuta cada 24 horas, comprobando los datos de los últimos 30 días
- **Cada 12 horas** : se ejecuta cada 12 horas, comprobando los datos de las últimas 24 horas
- **Cada 3 horas** : se ejecuta cada 3 horas y comprueba los datos de las últimas 6 horas.
- **Cada hora** : se ejecuta cada hora y se comprueban los datos de las últimas dos horas

>[!TIP]
> Hacer coincidir los filtros de tiempo de la consulta con la duración lookback. Se omiten los resultados fuera de la duración de lookback.  

Seleccione la frecuencia que coincida con el grado en el que desea supervisar las detecciones. Considere la capacidad de su organización para responder a las alertas.

### <a name="3-choose-the-impacted-entities"></a>3. Elija las entidades afectadas.
Identifique las columnas de los resultados de la consulta en las que espera buscar la entidad afectada principal o afectada. Por ejemplo, una consulta puede devolver direcciones de remitente ( `SenderFromAddress` o `SenderMailFromAddress` ) y destinatario ( `RecipientEmailAddress` ). La identificación de las columnas que representan la entidad afectada principal ayuda al servicio a agregar alertas relevantes, correlacionar incidentes y acciones de respuesta objetivo.

Puede seleccionar solo una columna para cada tipo de entidad (buzón, usuario o dispositivo). No se pueden seleccionar las columnas que no se devuelven mediante la consulta.

### <a name="4-specify-actions"></a>4. especificar acciones.
La regla de detección personalizada puede realizar acciones de forma automática en dispositivos, archivos o usuarios devueltos por la consulta.

#### <a name="actions-on-devices"></a>Acciones en dispositivos
Estas acciones se aplican a los dispositivos de la `DeviceId` columna de los resultados de la consulta:
- **Aislar dispositivo** : usa Microsoft defender para el punto de conexión para aplicar el aislamiento de red completo, lo que impide que el dispositivo se conecte a cualquier aplicación o servicio. [Más información acerca de Microsoft defender para el aislamiento de la máquina de extremo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **Collect Investigation Package** : recopila información de dispositivos en un archivo zip. [Obtenga más información sobre el paquete de investigación de Microsoft defender para extremo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **Ejecutar detección de virus** : realiza un examen completo del antivirus de Windows Defender en el dispositivo.
- **Iniciar investigación** : inicia una [investigación automatizada](mtp-autoir.md) en el dispositivo.
- **Restringir la ejecución** de la aplicación: establece restricciones en el dispositivo para permitir que solo se ejecuten los archivos firmados con un certificado emitido por Microsoft. [Obtenga más información sobre las restricciones de aplicaciones con Microsoft defender para Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Acciones en archivos
Al seleccionar esta opción, puede elegir aplicar la acción del **archivo de cuarentena** en los archivos de la `SHA1` columna,, `InitiatingProcessSHA1` `SHA256` o de los `InitiatingProcessSHA256` resultados de la consulta. Esta acción elimina el archivo de su ubicación actual y coloca una copia en cuarentena.

#### <a name="actions-on-users"></a>Acciones en los usuarios
Cuando se selecciona, la acción **marcar usuario como comprometedo** se lleva a cabo en los usuarios de la `AccountObjectId` `InitiatingProcessAccountObjectId` columna, o `RecipientObjectId` de los resultados de la consulta. Esta acción establece el nivel de riesgo de los usuarios en "alto" en Azure Active Directory, activando [las directivas de protección de identidad](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)correspondientes.

> [!NOTE]
> La acción permitir o bloquear para reglas de detección personalizadas no es compatible actualmente con Microsoft 365 defender.

### <a name="5-set-the-rule-scope"></a>5. establezca el ámbito de la regla.
Establezca el ámbito para especificar los dispositivos que cubre la regla. El ámbito influye en las reglas que comprueban los dispositivos y no afectan a las reglas que solo comprueban buzones de correo y cuentas de usuario o identidades.

Al establecer el ámbito, puede seleccionar:

- Todos los dispositivos
- Grupos de dispositivos específicos

Solo se consultarán los datos de los dispositivos en el ámbito. Además, las acciones solo se realizarán en estos dispositivos.

### <a name="6-review-and-turn-on-the-rule"></a>6. Revise y active la regla.
Después de revisar la regla, seleccione **crear** para guardarla. La regla de detección personalizada se ejecuta inmediatamente. Se ejecuta de nuevo en función de la frecuencia configurada para buscar coincidencias, generar alertas y tomar acciones de respuesta.

## <a name="manage-existing-custom-detection-rules"></a>Administración de reglas de detección personalizadas existentes
Puede ver la lista de reglas de detección personalizadas existentes, comprobar las ejecuciones anteriores y revisar las alertas que han desencadenado. También puede ejecutar una regla según demanda y modificarla.

### <a name="view-existing-rules"></a>Ver las reglas existentes

Para ver todas las reglas de detección personalizadas existentes, vaya a **búsqueda** de  >  **detecciones personalizadas**. La página enumera todas las reglas con la siguiente información de ejecución:

- **Última ejecución** : cuando se ejecutó una regla por última vez para buscar coincidencias de consulta y generar alertas
- **Último estado de ejecución** : Si una regla se ejecutó correctamente
- **Próxima ejecución** : la siguiente ejecución programada
- **Estado** : Si una regla se ha activado o desactivado

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Ver detalles de la regla, modificar regla y ejecutar regla

Para ver información completa sobre una regla de detección personalizada, vaya a **búsqueda**  >  de **detecciones personalizadas** y, a continuación, seleccione el nombre de la regla. A continuación, puede ver información general sobre la regla, incluida la información sobre su estado de ejecución y su ámbito. La página también proporciona la lista de alertas y acciones desencadenadas.

![Página de detalles de la regla de detección personalizada](../../media/custom-detection-details.png)<br>
*Detalles de la regla de detección personalizada*

También puede llevar a cabo las siguientes acciones en la regla de esta página:

- **Ejecutar** : ejecute la regla inmediatamente. Esto también restablece el intervalo para la siguiente ejecución.
- **Editar** : modificar la regla sin cambiar la consulta
- **Modificar consulta** : editar la consulta en la búsqueda avanzada
- **Activar**  /  **Desactivar** : habilitar la regla o impedir que se ejecute
- **Eliminar** : Desactive la regla y quítela

### <a name="view-and-manage-triggered-alerts"></a>Ver y administrar las alertas desencadenadas

En la pantalla detalles de la regla ( **búsqueda** de  >  **detecciones personalizadas**  >  **[nombre de la regla]** ), vaya a **alertas desencadenadas** , que enumera las alertas generadas por coincidencias en la regla. Seleccione una alerta para ver información detallada sobre ella y realizar las siguientes acciones:

- Administrar la alerta estableciendo su estado y clasificación (true o false Alert)
- Vincular la alerta a un incidente
- Ejecutar la consulta que desencadenó la alerta en la caza avanzada

### <a name="review-actions"></a>Revisión de acciones
En la pantalla detalles de la regla ( **búsqueda** de  >  **detecciones personalizadas**  >  **[nombre de la regla]** ), vaya a **acciones desencadenadas** , que enumera las acciones realizadas en función de las coincidencias de la regla.

>[!TIP]
>Para ver rápidamente información y realizar acciones en un elemento de una tabla, use la columna de selección [&#10003;] a la izquierda de la tabla.

## <a name="related-topic"></a>Tema relacionado
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Conozca el lenguaje de consulta de búsqueda avanzada](advanced-hunting-query-language.md)
