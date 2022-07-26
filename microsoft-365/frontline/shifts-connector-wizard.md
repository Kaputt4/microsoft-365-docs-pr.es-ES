---
title: Use el asistente del conector Turnos para conectar Turnos a Blue Yonder Workforce Management
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Obtenga información sobre cómo usar el asistente para conectores de Turnos para integrar Turnos en Teams con Blue Yonder Workforce Management.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 8c4aa1036af00eaaf7d776c267648141bf4db733
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "66998603"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>Use el asistente del conector Turnos para conectar Turnos a Blue Yonder Workforce Management

## <a name="overview"></a>Información general

El asistente para conectores de Turnos de la Centro de administración de Microsoft 365 permite integrar la aplicación Turnos en Microsoft Teams con el sistema de administración del personal (WFM). Después de configurar una conexión, los trabajadores de primera línea pueden ver y administrar sin problemas sus programaciones en Blue Yonder WFM desde Turnos.

El asistente configura el conector Shifts, crea una conexión con el sistema WFM y aplica la configuración de sincronización y las asignaciones de equipo que elija. La configuración de sincronización determina las características habilitadas en Turnos y la información de programación que se sincroniza entre Blue Yonder WFM y Turnos. Las asignaciones definen la relación de sincronización entre las instancias de Blue Yonder WFM y los equipos de Teams. Puede asignar a los equipos existentes y a los nuevos equipos.

Puede configurar varias conexiones, cada una con una configuración de sincronización diferente. Por ejemplo, si su organización tiene varias ubicaciones con requisitos de programación diferentes, cree una conexión con una configuración de sincronización única para cada ubicación. Tenga en cuenta que una instancia de Blue Yonder WFM solo se puede asignar a un equipo en un momento dado. Si una instancia ya está asignada a un equipo, no se puede asignar a otro equipo.

Con Blue Yonder WFM como sistema de registro, los trabajadores de primera línea pueden ver e intercambiar turnos, administrar su disponibilidad y solicitar permisos en turnos en sus dispositivos. Los administradores de primera línea pueden seguir usando Blue Yonder WFM para configurar programaciones.

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>Integración de turnos con Blue Yonder Workforce Management

Actualmente, el asistente admite el [conector Turnos de Microsoft Teams para Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder). Este conector le permite integrar Shifts con Blue Yonder Workforce Management (Blue Yonder WFM) para administrar las programaciones y mantenerlas actualizadas. En este artículo, le guiaremos a través de cómo ejecutar el asistente para configurar una conexión a Blue Yonder WFM a través del conector.

> [!NOTE]
> También puede usar PowerShell para integrar Shifts con Blue Yonder WFM. Para obtener más información, consulte [Usar PowerShell para administrar la conexión de Turnos a Workforce Management de Blue Yonder](shifts-connector-blue-yonder-powershell-setup.md).

## <a name="before-you-begin"></a>Antes de empezar

Debe ser administrador global de Microsoft 365 para ejecutar el asistente.

### <a name="prerequisites"></a>Requisitos previos
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](includes/shifts-connector-prerequisites.md)]

- Los equipos que desea asignar no tienen ninguna programación. Si un equipo tiene una programación existente, [quite la programación del equipo](#remove-schedules-from-teams-you-want-to-map) antes de asignarle una instancia de Blue Yonder WFM. De lo contrario, verá turnos duplicados.

## <a name="remove-schedules-from-teams-you-want-to-map"></a>Eliminación de programaciones de los equipos que desea asignar
<a name="remove_schedules"> </a>

> [!NOTE]
> Complete este paso si va a asignar instancias de Blue Yonder WFM a los equipos existentes. Si va a asignar a equipos que no tienen ninguna programación o si va a crear nuevos equipos a los que asignar, puede omitir este paso.

Use PowerShell para quitar programaciones de los equipos.

1. En primer lugar, tendrá que instalar los módulos de PowerShell y configurarse. Siga estos pasos para [configurar su entorno](shifts-connector-powershell-manage.md#set-up-your-environment):
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
1. Seleccione **Siguiente** para crear una conexión WFM Blue Yonder.

### <a name="enter-connection-details"></a>Escriba los detalles de la conexión.
<a name="connection_details"> </a>

1. En la página Detalles de la conexión, asigne un nombre único a la conexión. No puede tener más de 128 caracteres ni tener caracteres especiales.
    :::image type="content" source="media/shifts-connector-wizard-connection-details.png" alt-text="Captura de pantalla de la página Detalles de conexión del asistente, en la que se muestra la configuración de conexión." lightbox="media/shifts-connector-wizard-connection-details.png":::
1. El nombre de la cuenta de servicio de Blue Yonder WFM y las direcciones URL de servicio y contraseña:
1. Cuando haya terminado, seleccione **Siguiente** para probar la conexión con la configuración especificada.

### <a name="choose-sync-settings"></a>Elección de la configuración de sincronización
<a name="sync"> </a>

En la página Configuración de sincronización, elija la información que se va a sincronizar de Blue Yonder WFM a Shifts, la frecuencia de sincronización y si los usuarios de Shifts pueden realizar cambios en los datos.

1. Escriba su cuenta del sistema de Microsoft 365.
    :::image type="content" source="media/shifts-connector-wizard-sync-settings.png" alt-text="Captura de pantalla de la página Configuración de sincronización del asistente, en la que se muestra la configuración de sincronización." lightbox="media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. En **Notificaciones de correo electrónico de los destinatarios**, elija quién recibe notificaciones por correo electrónico sobre esta conexión. Puede agregar tanto usuarios individuales como grupos de seguridad a estos grupos. Las notificaciones por correo electrónico contienen información sobre el estado de la configuración de la conexión y cualquier problema o error que pueda producirse después de configurar la conexión.
1. Elija la configuración de sincronización:
    1. En **Programación y turnos**, elija los datos de Blue Yonder WFM que los usuarios de Turnos pueden ver o cambiar y, a continuación, establezca la frecuencia de sincronización.
    2. En **Solicitudes**, elija los tipos de solicitudes que los usuarios de Turnos pueden ver y crear.

    > [!IMPORTANT]
    > Si eligió cualquiera de las siguientes opciones para deshabilitar los turnos abiertos, las solicitudes de turnos abiertos, las solicitudes de intercambio o las solicitudes de tiempo de expiración, hay otro paso que debe realizar para ocultar la funcionalidad en Turnos.
    >
    > - Turnos abiertos: **los usuarios de desplazamientos no verán los datos de Blue Yonder WFM**
    > - Solicitudes de intercambio: **la característica está deshabilitada para todos los usuarios**
    > - Solicitudes de tiempo de espera: **la característica está deshabilitada para todos los usuarios**
    >
    > Después de ejecutar el asistente, asegúrese de seguir los pasos de la sección [Deshabilitar turnos abiertos, solicitudes de turnos abiertos, solicitudes de intercambio y solicitudes de tiempo de expiración](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) más adelante en este artículo.
 
1. Cuando haya terminado de elegir la configuración, seleccione **Crear conexión**.

### <a name="map-blue-yonder-workforce-management-instances-to-teams"></a>Asignación de instancias de Blue Yonder Workforce Management a equipos
<a name="sites"> </a>

Elija las instancias de Blue Yonder WFM que desea conectar a Shifts y, a continuación, asigne cada instancia a un equipo de Teams. Puede asignar hasta 100 instancias. Hay dos formas de hacerlo:

- [Asignación manual de instancias a equipos](#manually-map-instances-to-teams)
- [Preparación y carga de un archivo CSV que define las asignaciones](#use-a-csv-file-to-map-instances-to-teams)

#### <a name="manually-map-instances-to-teams"></a>Asignación manual de instancias a equipos

Seleccione las instancias que desea asignar.

:::image type="content" source="media/shifts-connector-wizard-sites.png" alt-text="Captura de pantalla del asistente, en la que se muestra la lista de instancias de Blue Yonder WFM." lightbox="media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a> A continuación, asigne cada instancia a un equipo de Teams. Puede asignar una instancia a un equipo existente o puede crear un nuevo equipo.
:::image type="content" source="media/shifts-connector-wizard-search-team.png" alt-text="Captura de pantalla del panel en la que se muestra la opción de equipo de búsqueda y se crea una nueva opción de equipo." lightbox="media/shifts-connector-wizard-search-team.png":::

##### <a name="to-map-an-instance-to-an-existing-team"></a>Para asignar una instancia a un equipo existente

1. Seleccione el nombre de la instancia.
2. En el panel, busque el equipo y selecciónelo. Tenga en cuenta que los equipos que ya están asignados a una instancia de esta conexión no aparecen en la búsqueda.
3. Elija la zona horaria y la ciudad más cercana.
4. Seleccione la opción **Guardar** y, a continuación, el botón **Siguiente**.

##### <a name="to-map-an-instance-to-a-new-team"></a>Para asignar una instancia a un nuevo equipo

1. Seleccione el nombre de la instancia.
2. En el panel, elija **Crear un nuevo equipo**. Se le llevará a una nueva pestaña en el explorador, donde puede crear un nuevo equipo en el Centro de administración de Microsoft 365.
    1. Escriba un nombre y una descripción opcional para la búsqueda.
    1. Agregue uno o varios propietarios de equipo. Asegúrese de agregar la cuenta del sistema de Microsoft 365 como propietario.
    1. Agregar miembros del equipo.
    1. Agregue una dirección de correo electrónico del equipo y elija una configuración de privacidad.
    1. Revise la configuración y, a continuación, elija **Agregar equipo**. Cuando se cree el equipo, elija **Cerrar**.
3. Volver al asistente, busque y seleccione el nuevo equipo que creó.
4. Elija la zona horaria y la ciudad más cercana.
5. Seleccione la opción **Guardar** y, a continuación, el botón **Siguiente**.

#### <a name="use-a-csv-file-to-map-instances-to-teams"></a>Uso de un archivo CSV para asignar instancias a equipos

1. Seleccione **Cambiar al modo masivo**.
1. Seleccione **Descargar un archivo de plantilla** para descargar una plantilla de asignación que puede usar para definir las asignaciones.

    :::image type="content" source="media/shifts-connector-wizard-mapping-file.png" alt-text="Captura de pantalla de la página Cargar archivo de asignación del asistente." lightbox="media/shifts-connector-wizard-mapping-file.png":::

1. Use la plantilla para crear el archivo de asignación. Contiene estas columnas, en el orden siguiente, empezando por la primera columna. Un asterisco (*) indica una columna necesaria.

    |Nombre de columna  |Descripción  |
    |---------|---------|
    |**Identificador de instancia de Blue Yonder*** |El identificador de instancia de Blue Yonder WFM.|
    |**Nombre de instancia de Blue Yonder**|El nombre de instancia de Blue Yonder WFM.|
    |**Id. de equipo*** |El identificador de equipo.|
    |**Nombre del equipo**|El nombre del equipo.|
    |**Zona horaria*** |Zona horaria en formato de base de datos tz. Por ejemplo, Europa/Londres.|

    > [!NOTE]
    > Solo tiene que rellenar las columnas necesarias (Identificador de instancia de Blue Yonder, Id. de equipo, Zona horaria) para asignar instancias a los equipos.

    Este es un ejemplo del aspecto de un archivo bloqueado en un dispositivo móvil:

    |Identificador de instancia de Blue Yonder|Nombre de instancia de Blue Yonder|Id. de equipo|Nombre del equipo|Zona horaria|
    |---------|---------|---------|---------|---------|
    |2111|Equipo de Contoso en EE. UU.|3a4d78a-2261|Equipo de EE. UU.|America/Los_Angeles|
    |3212|Equipo de Contoso del Reino Unido|2d1f6c2e-5272|Equipo del Reino Unido|Europe/London|
    |4865||bfa6o89e-1328||América/Toronto|

1. Cuando haya creado el archivo de asignación, seleccione **Examinar** para cargarlo. El asistente valida el archivo. Si encuentra errores, verá una lista de los errores y un mensaje en el que se solicita que los corrija. De lo contrario, verá un mensaje para continuar con el paso siguiente.  
1. Seleccione **Siguiente**.

### <a name="review-and-finish"></a>Revisar y finalizar

Revise la configuración. Si necesita realizar cambios en las asignaciones de equipo, elija **Editar** para hacerlo. Cuando esté listo, seleccione **Finalizar**.

:::image type="content" source="media/shifts-connector-wizard-review.png" alt-text="Captura de pantalla de la página Revisar del asistente, en la que se muestran las asignaciones." lightbox="media/shifts-connector-wizard-review.png":::

Verá un mensaje para confirmar que hemos recibido la solicitud junto con un identificador de operación. Anote el identificador de la operación. Lo necesitará para comprobar el estado de configuración de la conexión.

:::image type="content" source="media/shifts-connector-wizard-operation-id.png" alt-text="Captura de pantalla de la página del asistente, en la que se muestra el mensaje de confirmación y el identificador de la operación." lightbox="media/shifts-connector-wizard-operation-id.png":::

El asistente inicia el proceso para configurar la conexión y asignar las instancias a los equipos seleccionados. Esta sincronización puede tardar algún tiempo en completarse. Los destinatarios elegidos recibirán notificaciones por correo electrónico sobre el estado de la instalación.

Seleccione **Listo** para salir del asistente.

¡Está en camino, pero aún no ha terminado! Asegúrese de comprobar su correo electrónico. Recibirá una confirmación de que hemos recibido su solicitud junto con un [enlace](shifts-connector-powershell-manage.md#check-connection-setup-status) para comprobar el estado de la instalación.

> [!NOTE]
> Si se produce un problema o error en una conexión después de configurarla, recibirá una notificación por correo electrónico. Siga las instrucciones del correo electrónico para solucionar el problema.

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Deshabilitar turnos abiertos, solicitudes de turnos abiertos, solicitudes de intercambio y solicitudes de tiempo de expiración

> [!IMPORTANT]
> Siga estos pasos solo si elige cualquiera de las siguientes opciones para deshabilitar los turnos abiertos, las solicitudes de turnos abiertos, las solicitudes de intercambio o las solicitudes de tiempo de expiración en el asistente. Al completar este paso, se oculta la funcionalidad en Turnos.
>
> - Turnos abiertos: **los usuarios de desplazamientos no verán los datos de Blue Yonder WFM**
> - Solicitudes de intercambio: **la característica está deshabilitada para todos los usuarios**
> - Solicitudes de tiempo de espera: **la característica está deshabilitada para todos los usuarios**
>
> Sin este segundo paso, los usuarios seguirán viendo la funcionalidad en Turnos y recibirán un mensaje de error de "operación no admitida" si intentan usarlo.

Para ocultar turnos abiertos, solicitudes de intercambio y solicitudes de tiempo de espera en Turnos, use el tipo de [recurso de programación](/graph/api/resources/schedule) Graph API para establecer los parámetros ```false``` siguientes en para cada equipo que haya asignado a una instancia de Blue Yonder WFM:

- Abrir turnos: ```openShiftsEnabled```
- Solicitudes de intercambio: ```swapShiftsRequestsEnabled```
- Solicitudes de tiempo de expiración: ```timeOffRequestsEnabled```

Para ocultar las solicitudes de turnos abiertos en Turnos, vaya a **Configuración** en Turnos y, a continuación, desactive la opción **Abrir turnos**.

## <a name="if-you-need-to-make-changes-to-a-connection"></a>Si necesita realizar cambios en una conexión
<a name="update_connection"> </a>

Una vez configurada una conexión, use PowerShell para realizar cambios en ella. Por ejemplo, puede actualizar la configuración de sincronización, las asignaciones de equipo y deshabilitar la sincronización para una conexión. Para obtener información paso a paso, consulte [Usar PowerShell para administrar la conexión de Turnos a Workforce Management de Blue Yonder](shifts-connector-powershell-manage.md).

## <a name="related-articles"></a>Artículos relacionados

- [Conectores de Turnos](shifts-connectors.md)
- [Usar PowerShell para administrar la conexión de Turnos a Workforce Management de Blue Yonder](shifts-connector-powershell-manage.md)
- [Administrar la aplicación Turnos para su organización en Teams](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
