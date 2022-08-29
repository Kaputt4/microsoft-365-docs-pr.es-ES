---
title: Creación y administración de reglas de detección personalizadas en Microsoft 365 Defender
description: Aprenda a crear y administrar reglas de detecciones personalizadas basadas en consultas de búsqueda avanzadas.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, reglas, esquema, kusto, RBAC, permisos, Microsoft Defender para punto de conexión
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 0bc0ff6c0ccd9013685ff59e2ce3f12745a7e82e
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2022
ms.locfileid: "67387031"
---
# <a name="create-and-manage-custom-detections-rules"></a>Creación y administración de reglas de detecciones personalizadas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

Las reglas de detección personalizadas son reglas que puede diseñar y ajustar mediante consultas [de búsqueda avanzadas](advanced-hunting-overview.md) . Estas reglas le permiten supervisar proactivamente varios eventos y estados del sistema, incluida la sospecha de actividad de infracción y puntos de conexión mal configurados. Puede configurarlas para que se ejecuten a intervalos regulares, generando alertas y llevando a cabo acciones de respuesta siempre que haya coincidencias.

## <a name="required-permissions-for-managing-custom-detections"></a>Permisos necesarios para administrar detecciones personalizadas

Para administrar detecciones personalizadas, debe tener asignado uno de estos roles:

- **Administrador de seguridad**: los usuarios con este [rol de Azure Active Directory](/azure/active-directory/roles/permissions-reference#security-administrator) pueden administrar la configuración de seguridad en el portal de Microsoft 365 Defender y en otros portales y servicios.

- **Operador de seguridad**: los usuarios con este [rol de Azure Active Directory](/azure/active-directory/roles/permissions-reference#security-operator) pueden administrar alertas y tener acceso global de solo lectura a características relacionadas con la seguridad, incluida toda la información del portal de Microsoft 365 Defender. Este rol es suficiente para administrar las detecciones personalizadas solo si el control de acceso basado en rol (RBAC) está desactivado en Microsoft Defender para punto de conexión. Si tiene RBAC configurado, también necesita el permiso **administrar la configuración de seguridad** para Defender para punto de conexión.

También puede administrar las detecciones personalizadas que se aplican a los datos de soluciones de Microsoft 365 Defender específicas si tiene permisos para ellas. Si solo tiene permisos de administración para Microsoft 365 Defender para Office, por ejemplo, puede crear detecciones personalizadas mediante `Email` tablas, pero no `Identity` tablas.  

Para administrar los permisos necesarios, un **administrador global** puede:

- Asigne el rol **de administrador de seguridad** o **operador de seguridad** en [Centro de administración de Microsoft 365](https://admin.microsoft.com/) en **Roles** > **Administrador de seguridad**.
- Compruebe la configuración de RBAC para Microsoft Defender para punto de conexión en [Microsoft 365 Defender](https://security.microsoft.com/) en **Roles** **de permisos** >  **de configuración** > . Seleccione el rol correspondiente para asignar el permiso **administrar la configuración de seguridad** .

> [!NOTE]
> Para administrar detecciones personalizadas, **los operadores de seguridad** necesitarán el permiso **administrar la configuración de seguridad** en Microsoft Defender para punto de conexión si RBAC está activado.

## <a name="create-a-custom-detection-rule"></a>Creación de una regla de detección personalizada
### <a name="1-prepare-the-query"></a>1. Prepare la consulta.

En el portal de Microsoft 365 Defender, vaya a **Búsqueda avanzada** y seleccione una consulta existente o cree una nueva consulta. Al usar una nueva consulta, ejecútela para identificar errores y comprender los posibles resultados.

>[!IMPORTANT]
>Para evitar que el servicio devuelva demasiadas alertas, cada regla se limita a generar solo 100 alertas cada vez que se ejecuta. Antes de crear una regla, ajuste la consulta para evitar alertas de actividad normal diaria.


#### <a name="required-columns-in-the-query-results"></a>Columnas necesarias en los resultados de la consulta
Para crear una regla de detección personalizada, la consulta debe devolver las siguientes columnas:

- `Timestamp`: se usa para establecer la marca de tiempo de las alertas generadas
- `ReportId`: permite búsquedas de los registros originales.
- Una de las siguientes columnas que identifica dispositivos, usuarios o buzones específicos:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (remitente de sobre o dirección de la Ruta de Devolución),
    - `SenderMailFromAddress` (dirección de remitente mostrada por el cliente de correo electrónico).
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>Se agregará compatibilidad con entidades adicionales a medida que se agreguen nuevas tablas al [esquema de búsqueda avanzada](advanced-hunting-schema-tables.md).

Las consultas simples, como las que no usan el `project` operador o `summarize` para personalizar o agregar resultados, suelen devolver estas columnas comunes.

Hay varias maneras de garantizar que las consultas más complejas devuelvan estas columnas. Por ejemplo, si prefiere agregar y contar por entidad en una columna como `DeviceId`, todavía puede devolverla `Timestamp` y `ReportId` obtenerla del evento más reciente que implica cada único `DeviceId`.


> [!IMPORTANT]
> Evite filtrar las detecciones personalizadas mediante la `Timestamp` columna . Los datos usados para las detecciones personalizadas se filtran previamente en función de la frecuencia de detección.


La consulta de ejemplo siguiente cuenta el número de dispositivos únicos (`DeviceId`) con detecciones antivirus y usa este recuento para buscar solo los dispositivos con más de cinco detecciones. Para devolver la versión más reciente `Timestamp` y la correspondiente `ReportId`, usa el `summarize` operador con la `arg_max` función .

```kusto
DeviceEvents
| where ingestion_time() > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> Para mejorar el rendimiento de las consultas, establezca un filtro de tiempo que coincida con la frecuencia de ejecución prevista para la regla. Dado que la ejecución menos frecuente es _cada 24 horas_, el filtrado del último día cubrirá todos los datos nuevos.

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. Cree una nueva regla y proporcione detalles de alerta.

Con la consulta en el editor de consultas, seleccione **Crear regla de detección** y especifique los siguientes detalles de alerta:

- **Nombre de detección**: nombre de la regla de detección; debe ser único
- **Frecuencia**: intervalo para ejecutar la consulta y realizar acciones. [Consulte instrucciones adicionales a continuación.](#rule-frequency)
- **Título de alerta**: título mostrado con alertas desencadenadas por la regla; debe ser único
- **Gravedad**: riesgo potencial del componente o la actividad identificados por la regla
- **Categoría**: componente o actividad de amenaza identificados por la regla
- **MITRE ATT&técnicas de CK**: una o varias técnicas de ataque identificadas por la regla como se documenta en el [marco de MITRE ATT&CK](https://attack.mitre.org/). Esta sección está oculta para ciertas categorías de alertas, como malware, ransomware, actividad sospechosa y software no deseado
- **Descripción**: más información sobre el componente o la actividad identificados por la regla 
- **Acciones recomendadas**: acciones adicionales que los respondedores pueden realizar en respuesta a una alerta

#### <a name="rule-frequency"></a>Frecuencia de regla
Al guardar una nueva regla, se ejecuta y comprueba si hay coincidencias de los últimos 30 días de datos. A continuación, la regla se ejecuta de nuevo a intervalos fijos, aplicando una duración de devolución de la vista en función de la frecuencia que elija:

- **Cada 24 horas**: se ejecuta cada 24 horas, comprobando los datos de los últimos 30 días
- **Cada 12 horas**: se ejecuta cada 12 horas, comprobando los datos de las últimas 24 horas
- **Cada 3 horas**: se ejecuta cada 3 horas, comprobando los datos de las últimas 6 horas
- **Cada hora**: se ejecuta por hora, comprobando los datos de las últimas 2 horas

Al editar una regla, se ejecutará con los cambios aplicados en la siguiente hora de ejecución programada según la frecuencia que establezca. La frecuencia de la regla se basa en la marca de tiempo del evento y no en el tiempo de ingesta.



>[!TIP]
> Coincide con los filtros de tiempo de la consulta con la duración de la devolución de la vista. Los resultados fuera de la duración de la devolución de la vista se omiten.  

Seleccione la frecuencia que coincida con la proximidad con la que desea supervisar las detecciones. Tenga en cuenta la capacidad de su organización para responder a las alertas.

### <a name="3-choose-the-impacted-entities"></a>3. Elija las entidades afectadas.
Identifique las columnas de los resultados de la consulta donde espera encontrar la entidad principal afectada. Por ejemplo, una consulta podría devolver direcciones de remitente (`SenderFromAddress` o `SenderMailFromAddress`) y destinatario (`RecipientEmailAddress`). La identificación de cuál de estas columnas representa la entidad principal afectada ayuda al servicio a agregar alertas relevantes, correlacionar incidentes y acciones de respuesta al objetivo.

Solo puede seleccionar una columna para cada tipo de entidad (buzón, usuario o dispositivo). Las columnas que la consulta no devuelve no se pueden seleccionar.

### <a name="4-specify-actions"></a>4. Especifique acciones.
La regla de detección personalizada puede realizar automáticamente acciones en dispositivos, archivos o usuarios devueltos por la consulta.

#### <a name="actions-on-devices"></a>Acciones en dispositivos
Estas acciones se aplican a los dispositivos de la `DeviceId` columna de los resultados de la consulta:
- **Aislar dispositivo**: usa Microsoft Defender para punto de conexión para aplicar aislamiento de red completo, lo que impide que el dispositivo se conecte a cualquier aplicación o servicio. [Más información sobre Microsoft Defender para punto de conexión aislamiento de máquina](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **Recopilar paquete de investigación**: recopila información del dispositivo en un archivo ZIP. [Más información sobre el paquete de investigación de Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **Ejecución del examen antivirus**: realiza un examen completo del Antivirus de Microsoft Defender en el dispositivo
- **Iniciar investigación**: inicia una [investigación automatizada](m365d-autoir.md) en el dispositivo
- **Restringir la ejecución** de aplicaciones: establece restricciones en el dispositivo para permitir que solo se ejecuten los archivos que están firmados con un certificado emitido por Microsoft. [Más información sobre las restricciones de aplicaciones con Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Acciones en archivos
Cuando se selecciona, puede optar por aplicar la acción **Archivo de cuarentena** en los archivos de la `SHA1`columna , `InitiatingProcessSHA1`, `SHA256`o `InitiatingProcessSHA256` de los resultados de la consulta. Esta acción elimina el archivo de su ubicación actual y coloca una copia en cuarentena.

#### <a name="actions-on-users"></a>Acciones en usuarios
Cuando se selecciona, la acción **Marcar al usuario como comprometido** se toma en los usuarios de la columna `AccountObjectId`, `InitiatingProcessAccountObjectId` o `RecipientObjectId` en los resultados de la consulta. Esta acción establece el nivel de riesgo de los usuarios en "alto" en Azure Active Directory, desencadenando [las directivas de protección de identidades](/azure/active-directory/identity-protection/overview-identity-protection) correspondientes.

> [!NOTE]
> La acción de permitir o bloquear para las reglas de detección personalizadas no se admite actualmente en Microsoft 365 Defender.

### <a name="5-set-the-rule-scope"></a>5. Establezca el ámbito de la regla.
Establezca el ámbito para especificar qué dispositivos están cubiertos por la regla. El ámbito influye en las reglas que comprueban los dispositivos y no afectan a las reglas que solo comprueban buzones y cuentas de usuario o identidades.

Al establecer el ámbito, puede seleccionar:

- Todos los dispositivos
- Grupos de dispositivos específicos

Solo se consultarán los datos de dispositivos en el ámbito. Además, las acciones solo se realizarán en esos dispositivos.

### <a name="6-review-and-turn-on-the-rule"></a>6. Revise y active la regla.
Después de revisar la regla, seleccione **Crear** para guardarla. La regla de detección personalizada se ejecuta inmediatamente. Se ejecuta de nuevo en función de la frecuencia configurada para buscar coincidencias, generar alertas y realizar acciones de respuesta.


>[!Important] 
>Las detecciones personalizadas deben revisarse periódicamente para comprobar la eficacia y la eficacia. Para asegurarse de que está creando detecciones que desencadenan alertas verdaderas, tómese tiempo para revisar las detecciones personalizadas existentes siguiendo los pasos descritos en [Administración de reglas de detección personalizadas existentes](#manage-existing-custom-detection-rules). <br>  
Mantiene el control sobre la amplitud o la especificidad de las detecciones personalizadas, por lo que las alertas falsas generadas por las detecciones personalizadas podrían indicar la necesidad de modificar determinados parámetros de las reglas.


## <a name="manage-existing-custom-detection-rules"></a>Administrar reglas de detección personalizadas existentes
Puede ver la lista de reglas de detección personalizadas existentes, comprobar sus ejecuciones anteriores y revisar las alertas que han desencadenado. También puede ejecutar una regla a petición y modificarla.

>[!TIP]
> Las alertas que generan las detecciones personalizadas están disponibles a través de alertas y API de incidentes. Para obtener más información, consulte [API de Microsoft 365 Defender compatibles](api-supported.md).

### <a name="view-existing-rules"></a>Ver reglas existentes

Para ver todas las reglas de detección personalizadas existentes, vaya a **Buscar** > **reglas de detección personalizadas**. La página enumera todas las reglas con la siguiente información de la ejecución:

- **Última ejecución**: la última vez que se ejecutó una regla para comprobar si hay coincidencias de consulta y generar alertas
- **Estado de la última ejecución**: si una regla se ejecutó correctamente
- **Siguiente ejecución**: la siguiente ejecución programada
- **Estado**: si se ha activado o desactivado una regla

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Ver detalles, modificar y ejecutar la regla

Para ver información completa sobre una regla de detección personalizada, vaya a **Buscar** > **reglas de detección personalizadas** y, a continuación, seleccione el nombre de la regla. A continuación, puede ver información general sobre la regla, incluida la información sobre su estado de ejecución y ámbito. La página también proporciona la lista de alertas y acciones desencadenadas.

:::image type="content" source="../../media/custom-detect-rules-view.png" alt-text="Página detalles de la regla de detección personalizada en el portal de Microsoft 365 Defender" lightbox="../../media/custom-detect-rules-view.png":::<br>
*Detalles de la regla de detección personalizada*

También puede realizar las siguientes acciones en la regla desde esta página:

- **Ejecutar**: ejecute la regla inmediatamente. Esto también restablece el intervalo para la siguiente ejecución.
- **Editar**: modifique la regla sin cambiar la consulta.
- **Modificar consulta**: editar la consulta en la búsqueda avanzada
- **Prender** /  **Desactivar**: habilite la regla o impida que se ejecute.
- **Eliminar**: desactive la regla y quítelo.

### <a name="view-and-manage-triggered-alerts"></a>Ver y administrar alertas desencadenadas

En la pantalla de detalles de la regla (**Búsqueda** > **de detecciones** >  personalizadas **[Nombre de regla]**), vaya a **Alertas desencadenadas**, que enumera las alertas generadas por coincidencias con la regla. Seleccione una alerta para ver la información detallada al respecto y realizar las siguientes acciones:

- Administrar la alerta estableciendo su estado y clasificación (alerta verdadera o falsa).
- Vincular la alerta a un incidente.
- Ejecutar la consulta que desencadenó la alerta en la búsqueda avanzada.

### <a name="review-actions"></a>Revisar acciones
En la pantalla de detalles de la regla (**Búsqueda** > **de detecciones** >  personalizadas **[Nombre de regla]**), vaya a **Acciones desencadenadas**, que enumera las acciones realizadas en función de las coincidencias con la regla.

>[!TIP]
>Para ver rápidamente la información y realizar acciones en un elemento de una tabla, use la columna de selección [&#10003;] a la izquierda de la tabla.

>[!NOTE]
>Es posible que algunas columnas de este artículo no estén disponibles en Microsoft Defender para punto de conexión. [Active Microsoft 365 Defender](m365d-enable.md) para buscar amenazas mediante más orígenes de datos. Para mover los flujos de trabajo de búsqueda avanzados de Microsoft Defender para punto de conexión a Microsoft 365 Defender, siga los pasos descritos en [Migración de consultas de búsqueda avanzadas desde Microsoft Defender para punto de conexión](advanced-hunting-migrate-from-mde.md) .

## <a name="see-also"></a>Vea también
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Conozca el lenguaje de consulta de búsqueda avanzada](advanced-hunting-query-language.md)
- [Migración de consultas de búsqueda avanzadas desde Microsoft Defender para punto de conexión](advanced-hunting-migrate-from-mde.md)
