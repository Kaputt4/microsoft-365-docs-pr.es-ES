---
title: Creación y administración de reglas de detección personalizadas en protección contra amenazas de Microsoft
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: cea4dbcb42833a14980d092bd0ff168ca97e5934
ms.sourcegitcommit: 9489aaf255f8bf165e6debc574e20548ad82e882
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "46632156"
---
# <a name="create-and-manage-custom-detections-rules"></a>Creación y administración de reglas de detecciones personalizadas

**Se aplica a:**
- Protección contra amenazas de Microsoft

Las reglas de detección personalizadas creadas a partir de consultas de [caza avanzadas](advanced-hunting-overview.md) le permiten supervisar de forma proactiva varios eventos y Estados del sistema, como la actividad de infracciones y los extremos configurados incorrectamente. Puede establecer que se ejecuten a intervalos regulares, generando alertas y realizando acciones de respuesta siempre que haya coincidencias.

## <a name="required-permissions-for-managing-custom-detections"></a>Permisos necesarios para administrar detecciones personalizadas

Para administrar las detecciones personalizadas, debe tener asignado uno de estos roles:

- **Administrador** de seguridad: el rol de administrador de seguridad o administrador de seguridad es un [rol de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) para administrar varias configuraciones de seguridad en el centro de seguridad de Microsoft 365 y varios portales y servicios.

- **Operador de seguridad** : el rol de operador de seguridad es un [rol de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) para administrar alertas y tiene acceso global de solo lectura en características relacionadas con la seguridad, incluida toda la información en el centro de seguridad de Microsoft 365. Este rol es suficiente para administrar detecciones personalizadas solo si el control de acceso basado en roles (RBAC) está desactivado en ATP de Microsoft defender. Si tiene configurado un RBAC, también necesitará el permiso **administrar la configuración de seguridad** para ATP de Microsoft defender.

Para administrar los permisos necesarios, un **administrador global** puede hacer lo siguiente:

- Asigne el rol de **Administrador** de seguridad o **operador de seguridad** en el centro de administración de [Microsoft 365](https://admin.microsoft.com/) en **funciones**  >  **Administrador de seguridad**.
- Compruebe la configuración de RBAC para Microsoft defender ATP en el [centro de seguridad de Microsoft defender](https://securitycenter.windows.com/) en **configuración**  >  **Permissions**  >  **roles**de permisos. Seleccione el rol correspondiente para asignar el permiso **administrar la configuración de seguridad** .

> [!NOTE]
> Para administrar las detecciones personalizadas, los **operadores de seguridad** necesitarán el permiso administrar la **configuración de seguridad** en ATP de Microsoft defender si RBAC está activado.

## <a name="create-a-custom-detection-rule"></a>Crear una regla de detección personalizada
### <a name="1-prepare-the-query"></a>1. Prepare la consulta.

En el centro de seguridad de Microsoft 365, vaya a **búsqueda avanzada** y seleccione una consulta existente o cree una nueva consulta. Cuando use una consulta nueva, ejecute la consulta para identificar los errores y comprender los posibles resultados.

>[!IMPORTANT]
>Para evitar que el servicio devuelva demasiadas alertas, cada regla se limita a generar sólo 100 alertas cada vez que se ejecuta. Antes de crear una regla, ajuste su consulta para evitar alertas por actividades normales y cotidianas.


#### <a name="required-columns-in-the-query-results"></a>Columnas necesarias en los resultados de la consulta
Para crear una regla de detección personalizada, la consulta debe devolver las siguientes columnas:

- `Timestamp`
- Una de las siguientes columnas de dispositivo, usuario o buzón de correo:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress`(remitente del sobre o dirección de ruta de regreso)
    - `SenderMailFromAddress`(dirección del remitente mostrada por el cliente de correo electrónico)
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

Hay varias formas de garantizar que las consultas más complejas devuelven estas columnas. Por ejemplo, si prefiere agregar y contar por entidad en una columna como `DeviceId` , puede volver a `Timestamp` obtenerlo del evento más reciente que implique a cada único `DeviceId` .

La consulta de ejemplo siguiente cuenta el número de dispositivos únicos ( `DeviceId` ) con detecciones de antivirus y usa este recuento para buscar solo los dispositivos con más de cinco detecciones. Para devolver la última `Timestamp` , se usa el `summarize` operador con la `arg_max` función.

```kusto
DeviceEvents
| where ActionType == "AntivirusDetection"
| summarize Timestamp = max(Timestamp), count() by DeviceId, SHA1, InitiatingProcessAccountObjectId 
| where count_ > 5
```

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. cree una nueva regla y proporcione los detalles de la alerta.

Con la consulta en el editor de consultas, seleccione **crear regla de detección** y especifique los siguientes detalles de alerta:

- **Nombre de detección** : nombre de la regla de detección
- **Frecuencia** : intervalo para ejecutar la consulta y realizar una acción. [Consulte más información a continuación](#rule-frequency)
- **Título** de la alerta: título que se muestra con alertas desencadenadas por la regla
- **Gravedad** : riesgo potencial del componente o actividad identificados por la regla
- **Categoría** : componente de amenaza o actividad identificada por la regla
- **Mitre att&CK** : una o varias técnicas de ataque identificadas por la regla según se documenta en el [marco de MITRE de ATT&CK](https://attack.mitre.org/). Esta sección no se aplica y está oculta para determinadas categorías de alertas, incluidos malware, ransomware, actividades sospechosas y software no deseado.
- **Descripción** : más información sobre el componente o la actividad identificados por la regla 
- **Acciones recomendadas** : acciones adicionales que los respondedores pueden llevar a cabo en respuesta a una alerta

#### <a name="rule-frequency"></a>Frecuencia de la regla
Cuando se guarda, una regla de detección personalizada nueva o editada se ejecuta inmediatamente y comprueba si hay coincidencias de los últimos 30 días de datos. A continuación, la regla se ejecuta de nuevo a intervalos fijos y las duraciones de lookback en función de la frecuencia elegida:

- **Cada 24 horas** : se ejecuta cada 24 horas, comprobando los datos de los últimos 30 días
- **Cada 12 horas** : se ejecuta cada 12 horas, comprobando los datos de las últimas 24 horas
- **Cada 3 horas** : se ejecuta cada 3 horas y comprueba los datos de las últimas 6 horas.
- **Cada hora** : se ejecuta cada hora y se comprueban los datos de las últimas dos horas

Seleccione la frecuencia que coincida con el grado en el que desea supervisar las detecciones y considere la capacidad de su organización para responder a las alertas.

### <a name="3-choose-the-impacted-entities"></a>3. Elija las entidades afectadas.
Identifique las columnas de los resultados de la consulta en las que espera buscar la entidad afectada principal o afectada. Por ejemplo, una consulta puede devolver direcciones de remitente ( `SenderFromAddress` o `SenderMailFromAddress` ) y destinatario ( `RecipientEmailAddress` ). La identificación de las columnas que representan la entidad afectada principal ayuda al servicio a agregar alertas relevantes, correlacionar incidentes y acciones de respuesta objetivo.

Puede seleccionar solo una columna para cada tipo de entidad (buzón, usuario o dispositivo). No se pueden seleccionar las columnas que no se devuelven mediante la consulta.

### <a name="4-specify-actions"></a>4. especificar acciones.
La regla de detección personalizada puede realizar acciones de forma automática en dispositivos, archivos o usuarios devueltos por la consulta.

#### <a name="actions-on-devices"></a>Acciones en dispositivos
Estas acciones se aplican a los dispositivos de la `DeviceId` columna de los resultados de la consulta:
- **Aislar dispositivo** : usa ATP de Microsoft defender para aplicar el aislamiento de red completo, lo que impide que el dispositivo se conecte a cualquier aplicación o servicio. [Más información acerca del aislamiento de máquina ATP de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **Collect Investigation Package** : recopila información de dispositivos en un archivo zip. [Más información sobre el paquete de investigación ATP de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **Ejecutar detección de virus** : realiza un examen completo del antivirus de Windows Defender en el dispositivo.
- **Iniciar investigación** : inicia una [investigación automatizada](mtp-autoir.md) en el dispositivo.
- **Restringir la ejecución** de la aplicación: establece restricciones en el dispositivo para permitir que solo se ejecuten los archivos firmados con un certificado emitido por Microsoft. [Obtenga más información sobre las restricciones de aplicaciones con ATP de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Acciones en archivos
Al seleccionar esta opción, puede elegir aplicar la acción del **archivo de cuarentena** en los archivos de la `SHA1` columna,, `InitiatingProcessSHA1` `SHA256` o de los `InitiatingProcessSHA256` resultados de la consulta. Esta acción elimina el archivo de su ubicación actual y coloca una copia en cuarentena.

#### <a name="actions-on-users"></a>Acciones en los usuarios
Cuando se selecciona, la acción **marcar usuario como comprometedo** se lleva a cabo en los usuarios de la `AccountObjectId` `InitiatingProcessAccountObjectId` columna, o `RecipientObjectId` de los resultados de la consulta. Esta acción establece el nivel de riesgo de los usuarios en "alto" en Azure Active Directory, activando [las directivas de protección de identidad](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)correspondientes.

> [!NOTE]
> La acción permitir o bloquear para reglas de detección personalizadas no es compatible actualmente con la protección contra amenazas de Microsoft.

### <a name="5-set-the-rule-scope"></a>5. establezca el ámbito de la regla.
Establezca el ámbito para especificar los dispositivos que cubre la regla. El ámbito influye en las reglas que comprueban los dispositivos y no afectan a las reglas que solo comprueban buzones de correo y cuentas de usuario o identidades.

Al establecer el ámbito, puede seleccionar:

- Todos los dispositivos
- Grupos de dispositivos específicos

Solo se consultarán los datos de los dispositivos en el ámbito. Además, las acciones solo se realizarán en estos dispositivos.

### <a name="6-review-and-turn-on-the-rule"></a>6. Revise y active la regla.
Después de revisar la regla, haga clic en **crear** para guardarla. La regla de detección personalizada se ejecuta inmediatamente. Se ejecuta de nuevo en función de la frecuencia configurada para buscar coincidencias, generar alertas y tomar acciones de respuesta.

## <a name="manage-existing-custom-detection-rules"></a>Administración de reglas de detección personalizadas existentes
Puede ver la lista de reglas de detección personalizadas existentes, comprobar las ejecuciones anteriores y revisar las alertas que han desencadenado. También puede ejecutar una regla según demanda y modificarla.

### <a name="view-existing-rules"></a>Ver las reglas existentes

Para ver todas las reglas de detección personalizadas existentes, vaya a **búsqueda**de  >  **detecciones personalizadas**. La página enumera todas las reglas con la siguiente información de ejecución:

- **Última ejecución** : cuando se ejecutó una regla por última vez para buscar coincidencias de consulta y generar alertas
- **Último estado de ejecución** : Si una regla se ejecutó correctamente
- **Próxima ejecución** : la siguiente ejecución programada
- **Estado** : Si una regla se ha activado o desactivado

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Ver detalles de la regla, modificar regla y ejecutar regla

Para ver información completa acerca de una regla de detección personalizada, seleccione el nombre de la regla de la lista de reglas en la **caza**de  >  **detecciones personalizadas**. Se abrirá una página sobre la regla de detección personalizada con información general sobre la regla, incluidos los detalles de la alerta, el estado de ejecución y el ámbito. También proporciona la lista de alertas desencadenadas y desencadenadas.

![Página de detalles de la regla de detección personalizada](../../media/custom-detection-details.png)<br>
*Detalles de la regla de detección personalizada*

También puede llevar a cabo las siguientes acciones en la regla de esta página:

- **Ejecutar** : ejecute la regla inmediatamente. Esto también restablece el intervalo para la siguiente ejecución.
- **Editar** : modificar la regla sin cambiar la consulta
- **Modificar consulta** : editar la consulta en la búsqueda avanzada
- **Activar**  /  **Desactivar** : habilitar la regla o impedir que se ejecute
- **Eliminar** : Desactive la regla y quítela

### <a name="view-and-manage-triggered-alerts"></a>Ver y administrar las alertas desencadenadas

En la pantalla detalles de la regla (**búsqueda**de  >  **detecciones personalizadas**  >  **[nombre de la regla]**), vaya a **alertas desencadenadas** para ver la lista de alertas generadas por las coincidencias de la regla. Seleccione una alerta para ver información detallada sobre la misma y lleve a cabo las siguientes acciones en dicha alerta:

- Administrar la alerta estableciendo su estado y clasificación (true o false Alert)
- Vincular la alerta a un incidente
- Ejecutar la consulta que desencadenó la alerta en la caza avanzada

### <a name="review-actions"></a>Revisión de acciones
En la pantalla detalles de la regla (**búsqueda**de  >  **detecciones personalizadas**  >  **[nombre de la regla]**), vaya a **acciones desencadenadas** para ver la lista de acciones realizadas en función de las coincidencias en la regla.

>[!TIP]
>Para ver rápidamente información y realizar acciones en un elemento de una tabla, use la columna de selección [&#10003;] a la izquierda de la tabla.

## <a name="related-topic"></a>Tema relacionado
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Conozca el lenguaje de consulta de búsqueda avanzada](advanced-hunting-query-language.md)