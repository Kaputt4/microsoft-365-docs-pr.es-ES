---
title: Crear y administrar reglas de detección personalizadas en Microsoft 365 Defender
description: Aprenda a crear y administrar reglas de detecciones personalizadas basadas en consultas de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, detecciones personalizadas, reglas, esquema, kusto, microsoft 365, Protección contra amenazas de Microsoft, RBAC, permisos, ATP de Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 8c7e47e66f9e5543cc122c5b5154207cae836d2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932927"
---
# <a name="create-and-manage-custom-detections-rules"></a>Crear y administrar reglas de detecciones personalizadas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Las reglas de detección personalizadas son reglas que se pueden diseñar y modificar mediante consultas [de](advanced-hunting-overview.md) búsqueda avanzadas. Estas reglas le permiten supervisar de forma proactiva varios eventos y estados del sistema, incluida la actividad sospechosa de infracciones y los puntos de conexión mal configurados. Puedes configurarlos para que se ejecuten a intervalos regulares, generando alertas y llevando a cabo acciones de respuesta siempre que haya coincidencias.

## <a name="required-permissions-for-managing-custom-detections"></a>Permisos necesarios para administrar detecciones personalizadas

Para administrar las detecciones personalizadas, debe tener asignado uno de estos roles:

- **Administrador de seguridad:** los usuarios con este rol [de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) pueden administrar la configuración de seguridad en el Centro de seguridad de Microsoft 365 y otros portales y servicios.

- **Operador de seguridad:** los usuarios con este rol de [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) pueden administrar alertas y tener acceso global de solo lectura a las características relacionadas con la seguridad, incluida toda la información del Centro de seguridad de Microsoft 365. Este rol es suficiente para administrar detecciones personalizadas solo si el control de acceso basado en roles (RBAC) está desactivado en Microsoft Defender para Endpoint. Si tiene RBAC configurado, también necesita el permiso administrar la configuración **de seguridad** para Defender para Endpoint.

Para administrar los permisos necesarios, un **administrador global** puede:

- Asigne el rol **de administrador de seguridad** o operador **de** seguridad en el Centro de administración de [Microsoft 365](https://admin.microsoft.com/) en **Administración** de seguridad  >  **de roles.**
- Compruebe la configuración de RBAC de Microsoft Defender para Endpoint en el Centro [de seguridad de Microsoft Defender](https://securitycenter.windows.com/) en Roles **de** permisos  >  **de**  >  **configuración.** Seleccione el rol correspondiente para asignar el permiso **administrar la configuración de** seguridad.

> [!NOTE]
> Para administrar detecciones personalizadas,  los operadores de seguridad necesitarán el permiso administrar la configuración de seguridad en Microsoft Defender para Endpoint si RBAC está activado. 

## <a name="create-a-custom-detection-rule"></a>Crear una regla de detección personalizada
### <a name="1-prepare-the-query"></a>1. Prepare la consulta.

En el Centro de seguridad de Microsoft 365, vaya a Búsqueda **avanzada** y seleccione una consulta existente o cree una nueva consulta. Al usar una nueva consulta, ejecute la consulta para identificar errores y comprender los posibles resultados.

>[!IMPORTANT]
>Para evitar que el servicio devuelva demasiadas alertas, cada regla se limita a generar solo 100 alertas cada vez que se ejecuta. Antes de crear una regla, retocar la consulta para evitar alertas de actividad normal diaria.


#### <a name="required-columns-in-the-query-results"></a>Columnas necesarias en los resultados de la consulta
Para crear una regla de detección personalizada, la consulta debe devolver las siguientes columnas:

- `Timestamp`Se usa para establecer la marca de tiempo de las alertas generadas
- `ReportId`Habilita las búsquedas para los registros originales
- Una de las siguientes columnas que identifican dispositivos, usuarios o buzones específicos:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (remitente sobre o Return-Path dirección)
    - `SenderMailFromAddress` (Dirección del remitente mostrada por el cliente de correo electrónico)
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

Hay varias maneras de garantizar que las consultas más complejas devuelvan estas columnas. Por ejemplo, si prefiere agregar y contar por entidad bajo una columna como , todavía puede devolverlo y obtenerlo del evento más reciente que implica cada uno `DeviceId` `Timestamp` de los `ReportId` únicos `DeviceId` .

La consulta de ejemplo siguiente cuenta el número de dispositivos únicos ( ) con detecciones antivirus y usa este recuento para buscar solo los dispositivos con más `DeviceId` de cinco detecciones. Para devolver la última `Timestamp` y la `ReportId` correspondiente, usa el operador con la `summarize` `arg_max` función.

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> Para mejorar el rendimiento de las consultas, establezca un filtro de tiempo que coincida con la frecuencia de ejecución prevista para la regla. Dado que la ejecución menos frecuente es _cada 24 horas,_ el filtrado del día anterior abarcará todos los datos nuevos.

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. Cree una nueva regla y proporcione detalles de alerta.

Con la consulta en el editor de consultas, seleccione **Crear regla de detección** y especifique los siguientes detalles de alerta:

- **Nombre de la detección:** nombre de la regla de detección
- **Frecuencia:** intervalo para ejecutar la consulta y tomar medidas. [Consulta instrucciones adicionales a continuación](#rule-frequency)
- **Título de alerta:** título que se muestra con alertas desencadenadas por la regla
- **Gravedad:** posible riesgo del componente o actividad identificado por la regla
- **Categoría:** componente de amenaza o actividad identificada por la regla
- **MITRE ATT&técnicas de CK:** una o más técnicas de ataque identificadas por la regla como se documentan en el marco de [miTRE ATT&CK](https://attack.mitre.org/). Esta sección está oculta para determinadas categorías de alerta, como malware, ransomware, actividad sospechosa y software no deseado.
- **Descripción:** más información sobre el componente o la actividad identificados por la regla 
- **Acciones recomendadas:** acciones adicionales que los respondedores pueden realizar en respuesta a una alerta

#### <a name="rule-frequency"></a>Frecuencia de regla
Cuando guarda o edita una regla nueva, se ejecuta y comprueba si hay coincidencias de los últimos 30 días de datos. A continuación, la regla se ejecuta de nuevo a intervalos fijos, aplicando una duración de recuperación según la frecuencia que elija:

- **Cada 24 horas:** se ejecuta cada 24 horas, comprobando los datos de los últimos 30 días
- **Cada 12 horas:** se ejecuta cada 12 horas, comprobando los datos de las últimas 24 horas
- **Cada 3 horas:** se ejecuta cada 3 horas, comprobando los datos de las últimas 6 horas
- **Cada hora:** se ejecuta cada hora, comprobando los datos de las últimas 2 horas

>[!TIP]
> Hacer coincidir los filtros de tiempo de la consulta con la duración de la búsqueda. Los resultados fuera de la duración de la devolución se omiten.  

Seleccione la frecuencia que coincida con la proximidad con la que desea supervisar las detecciones. Tenga en cuenta la capacidad de su organización para responder a las alertas.

### <a name="3-choose-the-impacted-entities"></a>3. Elija las entidades afectadas.
Identifique las columnas de los resultados de la consulta donde espera encontrar la entidad principal afectada o afectada. Por ejemplo, una consulta puede devolver direcciones de remitente ( `SenderFromAddress` o ) y destinatario ( `SenderMailFromAddress` `RecipientEmailAddress` ). Identificar cuál de estas columnas representa la entidad afectada principal ayuda al servicio a agregar alertas relevantes, correlacionar incidentes y acciones de respuesta de destino.

Solo puede seleccionar una columna para cada tipo de entidad (buzón, usuario o dispositivo). Las columnas que no devuelve la consulta no se pueden seleccionar.

### <a name="4-specify-actions"></a>4. Especificar acciones.
La regla de detección personalizada puede realizar automáticamente acciones en dispositivos, archivos o usuarios devueltos por la consulta.

#### <a name="actions-on-devices"></a>Acciones en dispositivos
Estas acciones se aplican a los dispositivos de la `DeviceId` columna de los resultados de la consulta:
- **Aislar dispositivo:** usa Microsoft Defender para Endpoint para aplicar el aislamiento de red completo, evitando que el dispositivo se conecte a cualquier aplicación o servicio. [Más información sobre el aislamiento de la máquina de Microsoft Defender para endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **Recopilar paquete de investigación:** recopila información del dispositivo en un archivo ZIP. [Más información sobre el paquete de investigación de Microsoft Defender para puntos de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **Ejecutar examen antivirus:** realiza un análisis completo Windows Defender antivirus en el dispositivo
- **Iniciar investigación:** inicia una [investigación automatizada](mtp-autoir.md) en el dispositivo
- **Restringir la ejecución de** la aplicación: establece restricciones en el dispositivo para permitir que solo se ejecuten los archivos firmados con un certificado emitido por Microsoft. [Más información sobre las restricciones de la aplicación con Microsoft Defender para puntos de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Acciones en archivos
Cuando se selecciona, puede optar por aplicar la **acción** De poner en cuarentena archivo en los archivos de la `SHA1` , , o columna de los `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` resultados de la consulta. Esta acción elimina el archivo de su ubicación actual y coloca una copia en cuarentena.

#### <a name="actions-on-users"></a>Acciones en los usuarios
Cuando se selecciona, el usuario de marca **como acción** comprometida se toma en los usuarios de la columna , o en la columna de `AccountObjectId` los `InitiatingProcessAccountObjectId` `RecipientObjectId` resultados de la consulta. Esta acción establece el nivel de riesgo de los usuarios en "alto" en Azure Active Directory, lo que desencadena las directivas de [protección de identidades correspondientes.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)

> [!NOTE]
> La acción permitir o bloquear para reglas de detección personalizadas no se admite actualmente en Microsoft 365 Defender.

### <a name="5-set-the-rule-scope"></a>5. Establecer el ámbito de regla.
Establece el ámbito para especificar qué dispositivos están cubiertos por la regla. El ámbito influye en las reglas que comprueban dispositivos y no afecta a las reglas que solo comprueban buzones de correo, cuentas de usuario o identidades.

Al establecer el ámbito, puede seleccionar:

- Todos los dispositivos
- Grupos de dispositivos específicos

Solo se consultarán los datos de dispositivos en el ámbito. Además, las acciones solo se realizarán en esos dispositivos.

### <a name="6-review-and-turn-on-the-rule"></a>6. Revisar y activar la regla.
Después de revisar la regla, seleccione **Crear** para guardarla. La regla de detección personalizada se ejecuta inmediatamente. Se ejecuta de nuevo en función de la frecuencia configurada para buscar coincidencias, generar alertas y realizar acciones de respuesta.

## <a name="manage-existing-custom-detection-rules"></a>Administrar reglas de detección personalizadas existentes
Puedes ver la lista de reglas de detección personalizadas existentes, comprobar sus ejecuciones anteriores y revisar las alertas que han activado. También puede ejecutar una regla a petición y modificarla.

### <a name="view-existing-rules"></a>Ver reglas existentes

Para ver todas las reglas de detección personalizadas existentes, vaya **a**  >  **Detecciones personalizadas de búsqueda.** La página enumera todas las reglas con la siguiente información de ejecución:

- **Última ejecución:** cuando se ha ejecutado una regla por última vez para comprobar si hay coincidencias de consulta y generar alertas
- **Estado de la última ejecución:** si una regla se ejecutó correctamente
- **Siguiente ejecución:** la siguiente ejecución programada
- **Estado:** si se ha activado o desactivado una regla

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Ver detalles de la regla, modificar regla y ejecutar regla

Para ver información completa acerca de una regla de detección personalizada, vaya a Detecciones personalizadas de búsqueda y, a continuación,  >   seleccione el nombre de la regla. A continuación, puede ver información general sobre la regla, incluida la información sobre su estado de ejecución y ámbito. La página también proporciona la lista de alertas y acciones desencadenadas.

![Página de detalles de la regla de detección personalizada](../../media/custom-detection-details.png)<br>
*Detalles de la regla de detección personalizada*

También puede realizar las siguientes acciones en la regla desde esta página:

- **Ejecutar:** ejecute la regla inmediatamente. Esto también restablece el intervalo de la siguiente ejecución.
- **Editar:** modificar la regla sin cambiar la consulta
- **Modificar consulta:** editar la consulta en la búsqueda avanzada
- **Activar**  /  **Desactivar:** habilitar la regla o impedir que se ejecute
- **Eliminar:** desactivar la regla y quitarla

### <a name="view-and-manage-triggered-alerts"></a>Ver y administrar alertas desencadenadas

En la pantalla de detalles de la regla (**detecciones** personalizadas de búsqueda [nombre de regla] ), vaya a Alertas desencadenadas , que enumera las  >  **alertas generadas** por coincidencias  >  con la regla.  Seleccione una alerta para ver información detallada sobre ella y realizar las siguientes acciones:

- Administrar la alerta estableciendo su estado y clasificación (alerta verdadera o falsa)
- Vincular la alerta a un incidente
- Ejecutar la consulta que desencadenó la alerta en la búsqueda avanzada

### <a name="review-actions"></a>Revisar acciones
En la pantalla de detalles de la regla **(** detecciones personalizadas de búsqueda [nombre de regla] ), vaya a Acciones desencadenadas , que enumera las acciones realizadas en función de las  >  **coincidencias** con la  >   regla.

>[!TIP]
>Para ver rápidamente la información y realizar una acción en un elemento de una tabla, use la columna de selección [&#10003;] a la izquierda de la tabla.

## <a name="related-topic"></a>Tema relacionado
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Conozca el lenguaje de consulta de búsqueda avanzada](advanced-hunting-query-language.md)
