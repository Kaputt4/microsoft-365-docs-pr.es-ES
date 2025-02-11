---
title: Uso del asistente del conector Shifts para conectar shifts a ukg dimensiones
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: how-to
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Obtenga información sobre cómo usar el asistente para conectores Shifts para integrar Turnos en Teams con dimensiones ukg.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: e660bd7aa5cf34498f4c7e590c9eae5d09d23cea
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2022
ms.locfileid: "68786791"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-ukg-dimensions"></a>Uso del asistente del conector Shifts para conectar shifts a ukg dimensiones

## <a name="overview"></a>Información general

[!INCLUDE [preview-feature](includes/preview-feature.md)]

[!INCLUDE [shifts-connector-wizard-intro](includes/shifts-connector-wizard-intro.md)]

## <a name="integrate-shifts-with-ukg-dimensions"></a>Integración de turnos con dimensiones ukg

El [conector Turnos de Microsoft Teams para las dimensiones de UKG](shifts-connectors.md#microsoft-teams-shifts-connector-for-ukg-dimensions) le permite integrar Shifts con UKG Dimensions para administrar las programaciones y mantenerlas actualizadas. En este artículo, le guiaremos a través de cómo ejecutar el asistente para configurar una conexión a UKG Dimensions a través del conector.

> [!NOTE]
> También puede usar PowerShell para integrar Shifts con UKG Dimensions. Para más información, consulte [Uso de PowerShell para conectar turnos a dimensiones de UKG](shifts-connector-ukg-powershell-setup.md).

## <a name="before-you-begin"></a>Antes de empezar

Debe ser administrador global de Microsoft 365 para ejecutar el asistente.

<a name="prerequisites"> </a>
### <a name="prerequisites"></a>Requisitos previos
[!INCLUDE [shifts-connector-ukg-prerequisites](includes/shifts-connector-ukg-prerequisites.md)]

- Los equipos que desea asignar no tienen ninguna programación. Si un equipo tiene una programación existente, [quite la programación del equipo antes de](#remove-schedules-from-teams-you-want-to-map) asignarle una instancia de UKG Dimensions. De lo contrario, verá turnos duplicados.

<a name="remove_schedules"> </a>
## <a name="remove-schedules-from-teams-you-want-to-map"></a>Eliminación de programaciones de los equipos que desea asignar

> [!NOTE]
> Complete este paso si va a asignar instancias de UKG Dimensions a equipos existentes que tienen programaciones. Si va a asignar a equipos que no tienen ninguna programación o si va a crear nuevos equipos a los que asignar, puede omitir este paso.

Use PowerShell para quitar programaciones de los equipos.

1. En primer lugar, tendrá que instalar los módulos de PowerShell y configurarse. Siga los pasos para [configurar el entorno](shifts-connector-ukg-powershell-manage.md#set-up-your-environment).
1. Ejecute el comando siguiente:

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    Para obtener una lista de escenarios para el `EntityType` parámetro, ejecute [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector). Los datos de programación se quitarán para el intervalo de fecha y hora que especifique.

Para más información, vea [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord).

## <a name="run-the-wizard"></a>Ejecutar el asistente para la instalación

### <a name="get-started"></a>Introducción

1. En el panel de navegación izquierdo del [Centro de administración de Microsoft 365](https://admin.microsoft.com/), elija **Configuración** y, a continuación, vaya a la sección **Aplicaciones y correo electrónico**.
1. Seleccione **Conectar el sistema de administración de la fuerza de trabajo**. Aquí puede obtener más información sobre los conectores Shifts y la experiencia de trabajo y administrador de primera línea al conectar turnos al sistema de WFM.
    :::image type="content" source="media/shifts-connector-wizard-get-started.png" alt-text="Captura de pantalla de la página de detalles del Asistente para conectores Shifts en el Centro de administración de Microsoft 365." lightbox="media/shifts-connector-wizard-get-started.png":::
1. Cuando esté listo, seleccione **Comenzar**.
1. En la página Choose your connector (Elegir el conector), elija **UKG Dimensions (Dimensiones de UKG**) y, a continuación, seleccione **Siguiente** para crear una conexión UKG Dimensions.

<a name="connection_details"> </a>
### <a name="enter-connection-details"></a>Escriba los detalles de la conexión.

1. En la página Detalles de la conexión, asigne un nombre único a la conexión. No puede tener más de 128 caracteres ni tener caracteres especiales.
    :::image type="content" source="media/shifts-connector-wizard-ukg-connection-details.png" alt-text="Captura de pantalla de la página Detalles de conexión del asistente, en la que se muestra la configuración de conexión." lightbox="media/shifts-connector-wizard-ukg-connection-details.png":::
1. Escriba el nombre de la cuenta de servicio de UKG Dimensions (que permite el acceso a todas las instancias creadas en las dimensiones de UKG) y las direcciones URL de contraseña y servicio.
1. Cuando haya terminado, seleccione **Siguiente** para probar la conexión con la configuración especificada.

<a name="sync"> </a>
### <a name="choose-sync-settings"></a>Elección de la configuración de sincronización

En la página Configuración de sincronización, elija la información que se va a sincronizar de UkG Dimensions a Shifts, la frecuencia de sincronización y si los usuarios de Shifts pueden realizar cambios en los datos.

1. Escriba su cuenta del sistema de Microsoft 365.
    :::image type="content" source="media/shifts-connector-wizard-ukg-sync-settings.png" alt-text="Captura de pantalla de la página Configuración de sincronización del asistente, en la que se muestra la configuración de sincronización." lightbox="media/shifts-connector-wizard-ukg-sync-settings.png":::
<a name="email"> </a>
1. En **Notificaciones de correo electrónico de los destinatarios**, elija quién recibe notificaciones por correo electrónico sobre esta conexión. Puede agregar tanto usuarios individuales como grupos de seguridad a estos grupos. Las notificaciones por correo electrónico contienen información sobre el estado de la configuración de la conexión y cualquier problema o error que pueda producirse después de configurar la conexión.
1. Elija la configuración de sincronización:
    1. En **Programación y turnos**, elija los datos de dimensiones de UKG que desplazan los usuarios que pueden ver o cambiar y, a continuación, establezca la frecuencia de sincronización.
    1. En **Tarjeta de tiempo**, elija la acción que los usuarios pueden hacer con las entradas de tiempo.
    1. En **Solicitudes**, elija los tipos de solicitudes que los usuarios de Turnos pueden ver y crear.

    > [!IMPORTANT]
    > Si eligió cualquiera de las siguientes opciones para deshabilitar los turnos abiertos, las solicitudes de turnos abiertos, las solicitudes de intercambio o las solicitudes de tiempo de expiración, hay otro paso que debe realizar para ocultar la funcionalidad en Turnos.
    >
    > - Turnos abiertos: **desplazamientos que los usuarios no verán los datos de las dimensiones de UKG**
    > - Solicitudes de intercambio: **la característica está deshabilitada para todos los usuarios**
    > - Solicitudes de tiempo de espera: **la característica está deshabilitada para todos los usuarios**
    >
    > Después de ejecutar el asistente, asegúrese de seguir los pasos de la sección [Deshabilitar turnos abiertos, solicitudes de turnos abiertos, solicitudes de intercambio y solicitudes de tiempo de expiración](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) más adelante en este artículo.
 
1. Cuando haya terminado de elegir la configuración, seleccione **Crear conexión**.

<a name="instances"> </a>
### <a name="map-ukg-dimensions-instances-to-teams"></a>Asignación de instancias de UKG Dimensions a equipos

Elija las instancias de UKG Dimensions que desea conectar a Shifts y, a continuación, asigne cada instancia a un equipo de Teams. Puede asignar hasta 100 instancias. Hay dos formas de hacerlo:

- [Asignación manual de instancias a equipos](#manually-map-instances-to-teams)
- [Preparación y carga de un archivo CSV que define las asignaciones](#use-a-csv-file-to-map-instances-to-teams)

<a name="map_manual"> </a>
#### <a name="manually-map-instances-to-teams"></a>Asignación manual de instancias a equipos

Seleccione las instancias que desea asignar.

:::image type="content" source="media/shifts-connector-wizard-ukg-sites.png" alt-text="Captura de pantalla del asistente, en la que se muestra la lista de instancias de UKG Dimensions." lightbox="media/shifts-connector-wizard-ukg-sites.png":::

 A continuación, asigne cada instancia a un equipo de Teams. Puede asignar una instancia a un equipo existente o puede crear un nuevo equipo.
:::image type="content" source="media/shifts-connector-wizard-ukg-search-team.png" alt-text="Captura de pantalla del panel en la que se muestra la opción de equipo de búsqueda y se crea una nueva opción de equipo." lightbox="media/shifts-connector-wizard-ukg-search-team.png":::

[!INCLUDE [shifts-connector-manually-map-instances](includes/shifts-connector-manually-map-instances.md)]

<a name="map_csv"> </a>
#### <a name="use-a-csv-file-to-map-instances-to-teams"></a>Uso de un archivo CSV para asignar instancias a equipos

1. Seleccione **Cambiar al modo masivo**.
1. Seleccione **Descargar un archivo de plantilla** para descargar una plantilla de asignación que puede usar para definir las asignaciones.

    :::image type="content" source="media/shifts-connector-wizard-ukg-mapping-file.png" alt-text="Captura de pantalla de la página Cargar archivo de asignación del asistente." lightbox="media/shifts-connector-wizard-ukg-mapping-file.png":::

1. Use la plantilla para crear el archivo de asignación. Contiene estas columnas, en el orden siguiente, empezando por la primera columna. Un asterisco (*) indica una columna necesaria.

    |Nombre de columna  |Descripción  |
    |---------|---------|
    |**Id. de instancia de dimensiones de UKG*** |Las dimensiones de UKG WFM identificador de instancia.|
    |**Nombre de instancia de dimensiones de UKG**|Las dimensiones de UKG WFM nombre de instancia.|
    |**Id. de equipo*** |El identificador de equipo.|
    |**Nombre del equipo**|El nombre del equipo.|
    |**Zona horaria*** |Zona horaria en formato de base de datos tz. Por ejemplo, Europa/Londres.|

    > [!NOTE]
    > Solo tiene que rellenar las columnas necesarias (id. de instancia de dimensiones ukg, id. de equipo y zona horaria) para asignar instancias a los equipos.

    Para ayudarle a crear el archivo de asignación, la plantilla incluye una lista de todas las instancias de UKG Dimensions, seguida de una lista de los equipos (hasta 1000) y sus identificadores de equipo correspondientes.

    Este es un ejemplo del aspecto de un archivo bloqueado en un dispositivo móvil:

    |Id. de instancia de dimensiones de UKG|Nombre de instancia de dimensiones de UKG|Id. de equipo|Nombre del equipo|Zona horaria|
    |---------|---------|---------|---------|---------|
    |4201|CO/Australia|ee0bbc99-7120||Australia/Sydney|
    |4203|CO/US|90db4db7-be44|Equipo de EE. UU.|America/New_York|
    |4251||c88b4ead-c965||Europe/London|

1. Cuando haya creado el archivo de asignación, seleccione **Examinar** para cargarlo. El asistente valida el archivo. Si encuentra errores, verá una lista de los errores y un mensaje en el que se solicita que los corrija. De lo contrario, verá un mensaje para continuar con el paso siguiente.  
1. Seleccione **Siguiente**.

### <a name="review-and-finish"></a>Revisar y finalizar

Revise la configuración. Si necesita realizar cambios en las asignaciones de equipo, elija **Editar** para hacerlo. Cuando esté listo, seleccione **Finalizar**.

:::image type="content" source="media/shifts-connector-wizard-ukg-review.png" alt-text="Captura de pantalla de la página Revisar del asistente, en la que se muestran las asignaciones." lightbox="media/shifts-connector-wizard-ukg-review.png":::

Verá un mensaje para confirmar que hemos recibido la solicitud junto con un identificador de operación. Anote el identificador de la operación. Lo necesitará para comprobar el estado de configuración de la conexión.

:::image type="content" source="media/shifts-connector-wizard-ukg-operation-id.png" alt-text="Captura de pantalla de la página del asistente, en la que se muestra el mensaje de confirmación y el identificador de la operación." lightbox="media/shifts-connector-wizard-ukg-operation-id.png":::

El asistente inicia el proceso para configurar la conexión y asignar las instancias a los equipos seleccionados. Esta sincronización puede tardar algún tiempo en completarse. Los destinatarios elegidos recibirán notificaciones por correo electrónico sobre el estado de la instalación.

Seleccione **Listo** para salir del asistente.

¡Está en camino, pero aún no ha terminado! Asegúrese de comprobar su correo electrónico. Recibirá una confirmación de que hemos recibido su solicitud junto con un [enlace](shifts-connector-ukg-powershell-manage.md#check-connection-setup-status) para comprobar el estado de la instalación.

> [!NOTE]
> Si se produce un problema o error en una conexión después de configurarla, recibirá una notificación por correo electrónico. Siga las instrucciones del correo electrónico para solucionar el problema.

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Deshabilitar turnos abiertos, solicitudes de turnos abiertos, solicitudes de intercambio y solicitudes de tiempo de expiración

> [!IMPORTANT]
> Siga estos pasos solo si elige cualquiera de las siguientes opciones para deshabilitar los turnos abiertos, las solicitudes de turnos abiertos, las solicitudes de intercambio o las solicitudes de tiempo de expiración en el asistente. Al completar este paso, se oculta la funcionalidad en Turnos.
>
> - Turnos abiertos: **desplazamientos que los usuarios no verán los datos de las dimensiones de UKG**
> - Solicitudes de intercambio: **la característica está deshabilitada para todos los usuarios**
> - Solicitudes de tiempo de espera: **la característica está deshabilitada para todos los usuarios**
>
> Sin este segundo paso, los usuarios seguirán viendo la funcionalidad en Turnos y recibirán un mensaje de error de "operación no admitida" si intentan usarlo.

Para ocultar turnos abiertos, solicitudes de intercambio y solicitudes de tiempo de espera en Turnos, use el tipo de [recurso de programación](/graph/api/resources/schedule) Graph API para establecer los parámetros ```false``` siguientes en para cada equipo asignado a una instancia de UKG Dimensions:

- Abrir turnos: ```openShiftsEnabled```
- Solicitudes de intercambio: ```swapShiftsRequestsEnabled```
- Solicitudes de tiempo de expiración: ```timeOffRequestsEnabled```

Para ocultar las solicitudes de turnos abiertos en Turnos, vaya a **Configuración** en Turnos y, a continuación, desactive la opción **Abrir turnos**.

<a name="manage"> </a>
## <a name="manage-your-connection"></a>Administrar la conexión

Una vez configurada una conexión, puede administrar y realizar cambios en ella en el Centro de administración de Microsoft 365 o mediante PowerShell.

### <a name="use-the-microsoft-365-admin-center"></a>Use el Centro de administración de Microsoft 365

La página Administración de conectores muestra cada conexión que ha configurado, junto con información como el estado de mantenimiento y los detalles del intervalo de sincronización. También puede acceder al asistente para realizar cambios en cualquiera de las conexiones. Por ejemplo, puede actualizar la configuración de sincronización y las asignaciones de equipo.

Para obtener más información, consulte [Uso de la Centro de administración de Microsoft 365 para administrar la conexión shifts a las dimensiones de UKG](shifts-connector-ukg-admin-center-manage.md).

### <a name="use-powershell"></a>Usar PowerShell

Puede usar PowerShell para ver un informe de errores, cambiar la configuración de conexión, deshabilitar la sincronización, etc. Para obtener instrucciones paso a paso, consulte [Uso de PowerShell para administrar la conexión de Shifts a las dimensiones de UKG](shifts-connector-ukg-powershell-manage.md).

## <a name="related-articles"></a>Artículos relacionados

- [Conectores de Turnos](shifts-connectors.md)
- [Administrar la aplicación Turnos para su organización en Teams](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
