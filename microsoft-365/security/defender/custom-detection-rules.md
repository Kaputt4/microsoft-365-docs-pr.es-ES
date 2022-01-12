---
title: Crear y administrar reglas de detección personalizadas en Microsoft 365 Defender
description: Obtenga información sobre cómo crear y administrar reglas de detecciones personalizadas basadas en consultas avanzadas de búsqueda
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, reglas, esquema, kusto, RBAC, permisos, Microsoft Defender para endpoint
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
ms.openlocfilehash: 1de43dbf64709e5e38caffbe5af0a8bbf37f0d2a
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61940179"
---
# <a name="create-and-manage-custom-detections-rules"></a>Crear y administrar reglas de detecciones personalizadas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

Las reglas de detección personalizadas son reglas que puedes diseñar y ajustar [con](advanced-hunting-overview.md) consultas avanzadas de búsqueda. Estas reglas le permiten supervisar proactivamente varios eventos y estados del sistema, incluidos la actividad de infracción sospechosa y los extremos mal configurados. Puede configurarlas para que se ejecuten a intervalos regulares, generando alertas y llevando a cabo acciones de respuesta siempre que haya coincidencias.

## <a name="required-permissions-for-managing-custom-detections"></a>Permisos necesarios para administrar detecciones personalizadas

Para administrar detecciones personalizadas, debe tener asignado uno de estos roles:

- **Administrador de** seguridad: los usuarios [con este Azure Active Directory pueden](/azure/active-directory/roles/permissions-reference#security-administrator) administrar la configuración de seguridad en el portal de Microsoft 365 Defender y otros portales y servicios.

- **Operador de** seguridad: los usuarios con este rol Azure Active Directory pueden administrar alertas y tener acceso global de solo lectura [a](/azure/active-directory/roles/permissions-reference#security-operator) características relacionadas con la seguridad, incluida toda la información del portal Microsoft 365 Defender seguridad. Este rol es suficiente para administrar detecciones personalizadas solo si el control de acceso basado en roles (RBAC) está desactivado en Microsoft Defender para endpoint. Si tiene RBAC configurado, también necesita el permiso administrar la configuración **de seguridad** para Defender para endpoint.

También puede administrar detecciones personalizadas que se aplican a los datos de soluciones Microsoft 365 Defender específicas si tiene permisos para ellas. Si solo tiene permisos para administrar Microsoft 365 Defender para Office, por ejemplo, puede crear detecciones personalizadas con tablas, pero `Email` no `Identity` tablas.  

Para administrar los permisos necesarios, un **administrador global** puede:

- Asigne el **rol de administrador de** seguridad o operador **de** seguridad [en Centro de administración de Microsoft 365](https://admin.microsoft.com/) en **Roles**  >  **Security admin**.
- Compruebe la configuración de RBAC para Microsoft Defender para endpoint [en Microsoft 365 Defender](https://security.microsoft.com/) en **Configuración** Roles  >  **de permisos**  >  . Seleccione el rol correspondiente para asignar el **permiso administrar la configuración de** seguridad.

> [!NOTE]
> Para administrar detecciones personalizadas,  los operadores de seguridad necesitarán el permiso administrar la configuración de seguridad en Microsoft Defender para endpoint si RBAC está activado. 

## <a name="create-a-custom-detection-rule"></a>Crear una regla de detección personalizada
### <a name="1-prepare-the-query"></a>1. Prepare la consulta.

En el portal Microsoft 365 Defender, vaya a **Búsqueda avanzada** y seleccione una consulta existente o cree una nueva consulta. Al usar una nueva consulta, ejecútela para identificar errores y comprender los posibles resultados.

>[!IMPORTANT]
>Para evitar que el servicio devuelva demasiadas alertas, cada regla se limita a generar solo 100 alertas cada vez que se ejecuta. Antes de crear una regla, ajuste la consulta para evitar alertas de actividad normal diaria.


#### <a name="required-columns-in-the-query-results"></a>Columnas necesarias en los resultados de la consulta
Para crear una regla de detección personalizada, la consulta debe devolver las siguientes columnas:

- `Timestamp`— se usa para establecer la marca de tiempo de las alertas generadas
- `ReportId`: habilita las búsquedas de los registros originales
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
>Se agregará compatibilidad con entidades adicionales a medida que se agregan nuevas tablas al [esquema de búsqueda avanzada.](advanced-hunting-schema-tables.md)

Las consultas simples, como las que no usan el operador or para personalizar o agregar resultados, normalmente `project` `summarize` devuelven estas columnas comunes.

Hay varias maneras de garantizar que las consultas más complejas devuelvan estas columnas. Por ejemplo, si prefiere agregar y contar por entidad debajo de una columna como , todavía puede devolver y obtenerlo del evento más reciente que implica cada `DeviceId` `Timestamp` único `ReportId` `DeviceId` .


> [!IMPORTANT]
> Evite filtrar detecciones personalizadas mediante la `Timestamp` columna. Los datos usados para las detecciones personalizadas se filtran previamente en función de la frecuencia de detección.


La consulta de ejemplo siguiente cuenta el número de dispositivos únicos ( ) con detecciones antivirus y usa este recuento para buscar solo los dispositivos con más `DeviceId` de cinco detecciones. Para devolver el último `Timestamp` y el correspondiente , usa el operador con la `ReportId` `summarize` `arg_max` función.

```kusto
DeviceEvents
| where ingestion_time() > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> Para obtener un mejor rendimiento de consulta, establezca un filtro de tiempo que coincida con la frecuencia de ejecución prevista para la regla. Dado que la ejecución menos frecuente es _cada 24 horas,_ el filtrado del último día cubrirá todos los datos nuevos.

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. Cree una nueva regla y proporcione detalles de alerta.

Con la consulta en el editor de consultas, seleccione **Crear regla de detección** y especifique los siguientes detalles de alerta:

- **Nombre de detección**: nombre de la regla de detección
- **Frecuencia:** intervalo para ejecutar la consulta y realizar acciones. [Vea instrucciones adicionales a continuación](#rule-frequency)
- **Título de alerta:** título que se muestra con alertas desencadenadas por la regla
- **Gravedad:** riesgo potencial del componente o actividad identificado por la regla
- **Categoría**: componente de amenaza o actividad identificada por la regla
- **MITRE ATT&técnicas de CK**: una o más técnicas de ataque identificadas por la regla como documentadas en el marco de&[CK de MITRE ATT](https://attack.mitre.org/). Esta sección está oculta para determinadas categorías de alertas, como malware, ransomware, actividad sospechosa y software no deseado
- **Descripción:** más información sobre el componente o la actividad identificada por la regla 
- **Acciones recomendadas:** acciones adicionales que los respondedores pueden realizar en respuesta a una alerta

#### <a name="rule-frequency"></a>Frecuencia de regla
Al guardar una nueva regla, se ejecuta y comprueba las coincidencias de los últimos 30 días de datos. A continuación, la regla se ejecuta de nuevo a intervalos fijos, aplicando una duración de devolución basada en la frecuencia que elija:

- **Cada 24 horas:** se ejecuta cada 24 horas, comprobando los datos de los últimos 30 días
- **Cada 12 horas:** se ejecuta cada 12 horas, comprobando los datos de las últimas 24 horas
- **Cada 3 horas:** se ejecuta cada 3 horas, comprobando los datos de las últimas 6 horas
- **Cada hora:** se ejecuta cada hora, comprobando los datos de las últimas 2 horas

Al editar una regla, se ejecutará con los cambios aplicados en la siguiente hora de ejecución programada según la frecuencia que establezca.



>[!TIP]
> Coincide con los filtros de tiempo de la consulta con la duración de la devolución. Se omiten los resultados fuera de la duración de la devolución.  

Seleccione la frecuencia que coincida con la que desea supervisar las detecciones. Tenga en cuenta la capacidad de su organización para responder a las alertas.

### <a name="3-choose-the-impacted-entities"></a>3. Elija las entidades afectadas.
Identifique las columnas de los resultados de la consulta en las que espera encontrar la entidad principal afectada o afectada. Por ejemplo, una consulta puede devolver direcciones de remitente ( `SenderFromAddress` o ) y destinatario ( `SenderMailFromAddress` `RecipientEmailAddress` ). La identificación de cuál de estas columnas representa la entidad principal afectada ayuda al servicio a agregar alertas relevantes, correlacionar incidentes y acciones de respuesta al objetivo.

Solo puede seleccionar una columna para cada tipo de entidad (buzón, usuario o dispositivo). Las columnas que la consulta no devuelve no se pueden seleccionar.

### <a name="4-specify-actions"></a>4. Especifique acciones.
La regla de detección personalizada puede realizar automáticamente acciones en dispositivos, archivos o usuarios devueltos por la consulta.

#### <a name="actions-on-devices"></a>Acciones en dispositivos
Estas acciones se aplican a los dispositivos de la `DeviceId` columna de los resultados de la consulta:
- **Aislar dispositivo:** usa Microsoft Defender para Endpoint para aplicar aislamiento total de red, lo que impide que el dispositivo se conecte a cualquier aplicación o servicio. [Más información sobre el aislamiento de la máquina de Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **Recopilar paquete de investigación:** recopila información del dispositivo en un archivo ZIP. [Obtenga más información sobre el paquete de investigación de Microsoft Defender para endpoints](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **Ejecutar examen antivirus:** realiza un examen Antivirus de Windows Defender completo en el dispositivo
- **Iniciar investigación:** inicia una [investigación automatizada](m365d-autoir.md) en el dispositivo
- **Restringir la ejecución de** aplicaciones: establece restricciones en el dispositivo para permitir que solo se ejecuten los archivos que están firmados con un certificado emitido por Microsoft. [Más información sobre las restricciones de la aplicación con Microsoft Defender para endpoint](/microsoft-365/security/defender-endpoint/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Acciones en archivos
Cuando se selecciona, puede optar por aplicar la acción Archivo **de** cuarentena en los archivos de `SHA1` la columna , , o de los `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` resultados de la consulta. Esta acción elimina el archivo de su ubicación actual y coloca una copia en cuarentena.

#### <a name="actions-on-users"></a>Acciones en usuarios
Cuando se selecciona, la acción **Marcar al usuario como comprometido** se toma en los usuarios de la columna `AccountObjectId`, `InitiatingProcessAccountObjectId` o `RecipientObjectId` en los resultados de la consulta. Esta acción establece el nivel de riesgo de los usuarios en "alto" en Azure Active Directory, desencadenando las directivas [de protección de identidades correspondientes.](/azure/active-directory/identity-protection/overview-identity-protection)

> [!NOTE]
> La acción permitir o bloquear para reglas de detección personalizadas actualmente no se admite en Microsoft 365 Defender.

### <a name="5-set-the-rule-scope"></a>5. Establezca el ámbito de regla.
Establezca el ámbito para especificar los dispositivos cubiertos por la regla. El ámbito influye en las reglas que comprueban los dispositivos y no afectan a las reglas que solo comprueban buzones y cuentas de usuario o identidades.

Al establecer el ámbito, puede seleccionar:

- Todos los dispositivos
- Grupos de dispositivos específicos

Solo se consultarán los datos de dispositivos en el ámbito. Además, las acciones solo se realizarán en esos dispositivos.

### <a name="6-review-and-turn-on-the-rule"></a>6. Revise y active la regla.
Después de revisar la regla, seleccione **Crear** para guardarla. La regla de detección personalizada se ejecuta inmediatamente. Se ejecuta de nuevo en función de la frecuencia configurada para buscar coincidencias, generar alertas y realizar acciones de respuesta.


>[!Important] 
>Las detecciones personalizadas deben revisarse periódicamente para obtener eficacia y eficacia. Para asegurarse de que está creando detecciones que desencadenan alertas verdaderas, dedícalse a revisar las detecciones personalizadas existentes siguiendo los pasos descritos en Administrar reglas de detección [personalizadas existentes.](#manage-existing-custom-detection-rules) <br>  
Se mantiene el control sobre la generalidad o especificidad de las detecciones personalizadas, por lo que cualquier alerta falsa generada por detecciones personalizadas puede indicar la necesidad de modificar determinados parámetros de las reglas.


## <a name="manage-existing-custom-detection-rules"></a>Administrar reglas de detección personalizadas existentes
Puede ver la lista de reglas de detección personalizadas existentes, comprobar sus ejecuciones anteriores y revisar las alertas que han desencadenado. También puede ejecutar una regla a petición y modificarla.

>[!TIP]
> Las alertas generadas por detecciones personalizadas están disponibles en las API de alertas e incidentes. Para obtener más información, vea [Supported Microsoft 365 Defender API](api-supported.md).

### <a name="view-existing-rules"></a>Ver reglas existentes

Para ver todas las reglas de detección personalizadas existentes, vaya a **Buscar**  >  **reglas de detección personalizadas.** La página enumera todas las reglas con la siguiente información de la ejecución:

- **Última ejecución:** cuando se ejecuta por última vez una regla para comprobar si hay coincidencias de consulta y generar alertas
- **Estado de la última ejecución:** si una regla se ejecutó correctamente
- **Siguiente ejecución**: la siguiente ejecución programada
- **Estado:** si se ha activado o desactivado una regla

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Ver detalles, modificar y ejecutar la regla

Para ver información completa acerca de una regla de detección personalizada, vaya a **Buscar** reglas de detección personalizadas y, a continuación,  >   seleccione el nombre de la regla. A continuación, puede ver información general sobre la regla, incluida la información sobre su estado de ejecución y ámbito. La página también proporciona la lista de alertas y acciones desencadenadas.

![Página de detalles de regla de detección personalizada.](../../media/custom-detect-rules-view.png)<br>
*Detalles de la regla de detección personalizada*

También puede realizar las siguientes acciones en la regla desde esta página:

- **Ejecutar**: ejecute la regla inmediatamente. Esto también restablece el intervalo para la siguiente ejecución.
- **Editar**: modificar la regla sin cambiar la consulta
- **Modificar consulta**: editar la consulta en búsqueda avanzada
- **Activar**  /  **Desactivar :** habilitar la regla o impedir que se ejecute
- **Eliminar**: desactivar la regla y quitarla

### <a name="view-and-manage-triggered-alerts"></a>Ver y administrar alertas desencadenadas

En la pantalla de detalles de la regla (**Buscar** detecciones personalizadas [Nombre de regla] ), vaya a Alertas desencadenadas , que enumera las alertas generadas por  >  **coincidencias**  >  con la regla.  Seleccione una alerta para ver la información detallada al respecto y realizar las siguientes acciones:

- Administrar la alerta estableciendo su estado y clasificación (alerta verdadera o falsa).
- Vincular la alerta a un incidente.
- Ejecutar la consulta que desencadenó la alerta en la búsqueda avanzada.

### <a name="review-actions"></a>Revisar acciones
En la pantalla de detalles de la regla (**Buscar** detecciones personalizadas [Nombre de regla] ), vaya a Acciones desencadenadas , que enumera las acciones realizadas en función de las  >  **coincidencias**  >  con la regla. 

>[!TIP]
>Para ver rápidamente la información y realizar acciones en un elemento de una tabla, use la columna de selección [&#10003;] a la izquierda de la tabla.

>[!NOTE]
>Es posible que algunas columnas de este artículo no estén disponibles en Microsoft Defender para endpoint. [Activa la Microsoft 365 Defender](m365d-enable.md) para buscar amenazas con más orígenes de datos. Puede mover los flujos de trabajo de búsqueda avanzados de Microsoft Defender para endpoint a Microsoft 365 Defender siguiendo los pasos descritos en Migrar consultas avanzadas de búsqueda desde [Microsoft Defender para endpoint](advanced-hunting-migrate-from-mde.md).

## <a name="see-also"></a>Vea también
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Conozca el lenguaje de consulta de búsqueda avanzada](advanced-hunting-query-language.md)
- [Migrar consultas de búsqueda avanzada desde Microsoft Defender para endpoint](advanced-hunting-migrate-from-mde.md)
