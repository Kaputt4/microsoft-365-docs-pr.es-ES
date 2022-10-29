---
title: Conectores de Turnos
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: conceptual
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Obtenga información sobre los conectores de turnos y cómo usarlos para conectar turnos a su sistema de administración de personal.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 0a84f78dead461069a45c3b0cd4e19c2c024fd66
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2022
ms.locfileid: "68786725"
---
# <a name="shifts-connectors"></a>Conectores de Turnos

## <a name="overview"></a>Información general

Los conectores de turnos le permiten integrar Turnos, la herramienta de administración de programaciones en Microsoft Teams, con el sistema de administración de personal (workforce management, WFM). Después de configurar una conexión, los trabajadores de primera línea pueden ver y administrar sin problemas sus programaciones en Blue Yonder WFM desde Turnos.

La conexión del sistema de WFM a Teams permite a los empleados de primera línea administrar programaciones de forma más eficaz y simplifica los procesos diarios para lograr una mayor participación y productividad. Los trabajadores de primera línea tienen un lugar para que su programación, comunicación y colaboración tengan que realizar el trabajo, desde cualquier lugar y en cualquier dispositivo.

En este artículo se proporciona información general sobre los conectores de turnos y cómo funcionan.

## <a name="how-shifts-connectors-work"></a>Funcionamiento de los conectores de turnos

Los conectores sincronizan los datos de programación entre el sistema de WFM y los turnos, lo que lleva las programaciones de la organización a Teams. Los turnos son los lugares en los que los trabajadores de primera línea se involucran para sus necesidades de programación. El sistema de WFM es el sistema de registro de reglas de negocio, cumplimiento e inteligencia.

Los flujos de datos a través del conector garantizan que las programaciones estén siempre actualizadas. Las programaciones del sistema de WFM se sincronizan con Turnos. Además, los cambios realizados en las programaciones de Turnos se sincronizan de nuevo con el sistema de WFM. Como sistema de registro, el sistema de WFM aplica todas las reglas de negocio antes de que los datos se guarden en Turnos.

<a name="prereq"> </a>
<a name="schedules"> </a>
## <a name="managed-shifts-connectors"></a>Conectores de turnos administrados

Los conectores de Turnos administrados son conectores desarrollados en colaboración con nuestros asociados. Los conectores administrados están hospedados y administrados por nosotros o nuestros asociados. Con los conectores administrados, solo se necesita una configuración mínima.

|Connector|Descripción|Requirements|
|---------|---------|---------|
|[Conector de turnos de Microsoft Teams para Blue Yonder](#microsoft-teams-shifts-connector-for-blue-yonder)|Use este conector para integrar Shifts con Blue Yonder Workforce Management. Microsoft hospeda y administra este conector.|Requisitos previos para configurar una conexión: <ul><li>Uso del [asistente del conector Shifts](shifts-connector-wizard.md#prerequisites) en el Centro de administración de Microsoft 365<br>Antes de ejecutar el asistente, [quite las programaciones de los equipos existentes que desea asignar](shifts-connector-wizard.md#remove-schedules-from-teams-you-want-to-map).</li><li>Uso de [PowerShell](shifts-connector-blue-yonder-powershell-setup.md#prerequisites)</li></ul>|
|[Conector turnos de Microsoft Teams para dimensiones ukg](#microsoft-teams-shifts-connector-for-ukg-dimensions)|Use este conector para integrar Shifts con UKG Dimensions. Microsoft hospeda y administra este conector.|Requisitos previos para configurar una conexión: <ul><li>Uso del [asistente del conector Shifts](shifts-connector-wizard-ukg.md#prerequisites) en el Centro de administración de Microsoft 365<br>Antes de ejecutar el asistente, [quite las programaciones de los equipos existentes que desea asignar](shifts-connector-wizard-ukg.md#remove-schedules-from-teams-you-want-to-map).</li><li>Uso de [PowerShell](shifts-connector-ukg-powershell-setup.md#prerequisites)</li></ul>|
|[Conector de Turnos Reflexis para Microsoft Teams](#reflexis-shifts-connector-for-microsoft-teams)|Use este conector para integrar Shifts con Reflexis Workforce Scheduler. Zebra hospeda y administra este conector. |Para obtener más información, vaya al sitio web de <https://connect.zebra.com/microsoft-connectors>.|

<a name="blue_yonder"> </a>
### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Conector de turnos de Microsoft Teams para Blue Yonder

El conector Turnos de Teams para Blue Yonder es una oferta de primera persona hospedada y administrada por Microsoft. Con este conector, puede integrar Shifts con Blue Yonder Workforce Management (Blue Yonder WFM) versiones 2020.3, 2021.1 o 2021.2 para administrar sus programaciones y mantenerlas actualizadas.  

> [!NOTE]
> Si tiene Blue Yonder WFM 2020.3 o 2021.1, aplique la revisión 2020.3.0.4 o 2021.1.0.3. Esta revisión corrige un problema por el que los usuarios reciben un mensaje de error persistente en Turnos. También corrige un problema que impide que los usuarios actualicen su disponibilidad en Turnos.

:::image type="content" source="media/shifts-connector-blue-yonder.png" alt-text="Captura de pantalla que muestra una solicitud de intercambio en Turnos en un dispositivo móvil, solicitud de aprobación en Teams en el escritorio y una programación en Blue Yonder WFM." lightbox="media/shifts-connector-blue-yonder.png":::

Los administradores de primera línea pueden:

- Publicar turnos y programaciones en Blue Yonder WFM y verlos en Turnos.
- Crear, administrar y asignar turnos abiertos en Blue Yonder WFM y verlos en Turnos.
- Asignar turnos abiertos creados en Blue Yonder WFM en Turnos.
- Crear, editar y eliminar el tiempo de expiración en Blue Yonder WFM y verlo en Turnos.
- Ver y aprobar las solicitudes de programación de los trabajadores tanto en los WFM azules como en los turnos.
- Establecer y actualizar la disponibilidad del trabajo en Blue Yonder WFM y vea en Turnos.

Los trabajadores de primera línea pueden:

- Ver sus turnos y horarios propios y de su equipo en Turnos.
- Solicitar tiempo de descuento, abrir turnos y cambiar turnos en Turnos.
- Establecer su disponibilidad en Turnos.

En la actualidad, no son compatibles:

- Agregar, editar, eliminar, guardar o publicar turnos en Turnos.
- Agregar, editar, eliminar, guardar o publicar el tiempo de expiración en Turnos.
- Agregar, editar, eliminar, guardar o publicar turnos abiertos en Turnos.

Cuando un administrador o trabajador de primera línea intente realizar cualquiera de estas acciones en Turnos, recibirá un mensaje para informarles de que la acción no es compatible.

#### <a name="example-scenario"></a>Escenario de ejemplo

Eden, un administrador, publica una programación en Blue Yonder WFM, que se sincroniza con Turnos en Teams a través del conector. Alex, un miembro del personal, recibe una notificación en Teams en su dispositivo móvil y ve su horario y turnos asignados.

Alex necesita coger tiempo libre y solicita un día libre mediante Turnos. La solicitud se envía a Blue Yonder WFM a través del conector. Blue Yonder WFM garantiza que la solicitud es compatible con las reglas de negocio y se crea la solicitud. Eden ve y aprueba la solicitud en Blue Yonder WFM y la aprobación se sincroniza con Teams. (Eden también puede ver y aprobar la solicitud en Turnos). Alex recibe una notificación en Teams de que su solicitud está aprobada y ve su programación actualizada.

Alex quiere cambiar un turno con un compañero de trabajo. En Turnos, Alex ve una lista de todos los turnos que son aptos para un intercambio basado en las reglas de negocio en Blue Yonder WFM. Alex elige un turno que está asignado actualmente a Gena. Gena recibe una notificación en Teams en su dispositivo móvil y acepta la solicitud de intercambio. Eden ve y aprueba la solicitud en Turnos, y la aprobación se sincroniza con Blue Yonder WFM. (Eden también puede ver y aprobar la solicitud en Blue Yonder WFM). Alex y Gena reciben una notificación en Teams y ven sus programaciones actualizadas.

#### <a name="set-up-a-connection-to-blue-yonder-workforce-management"></a>Configuración de una conexión a Blue Yonder Workforce Management

La integración de Shifts con Blue Yonder WFM mediante el conector se realiza en solo unos pasos. Puede usar el asistente del conector Shifts en el Centro de administración de Microsoft 365 para configurar rápidamente una conexión. El asistente configura el conector en función de la configuración que elija y cree la conexión. Si prefiere usar PowerShell, también proporcionamos scripts de PowerShell que puede usar para conectarse.

Para obtener instrucciones paso a paso, consulte:

- [Use el asistente del conector de Turnos para conectar Turnos a Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [Uso de PowerShell para conectar Turnos a Workforce Management de Blue Yonder](shifts-connector-blue-yonder-powershell-setup.md)

Una vez configurada una conexión, puede actualizar y cambiar la configuración de conexión en cualquier momento, según sea necesario. Para más información, vea:

- [Use la Centro de administración de Microsoft 365 para administrar la conexión de Shifts a Blue Yonder Workforce Management](shifts-connector-blue-yonder-admin-center-manage.md)
- [Usar PowerShell para administrar la conexión de Turnos a Workforce Management de Blue Yonder](shifts-connector-powershell-manage.md)

En cuanto al conector en sí, no es necesario preocuparse por las actualizaciones o el mantenimiento. Nosotros nos encargaremos de eso.

### <a name="microsoft-teams-shifts-connector-for-ukg-dimensions"></a>Conector turnos de Microsoft Teams para dimensiones ukg

[!INCLUDE [preview-feature](includes/preview-feature.md)]

El conector Turnos de Teams para las dimensiones de UKG es una oferta de primera persona hospedada y administrada por Microsoft. Con este conector, puede integrar Shifts con UKG Dimensions para administrar las programaciones y mantenerlas actualizadas.  

:::image type="content" source="media/shifts-connector-ukg-dimensions.png" alt-text="Captura de pantalla en la que se muestran los cambios en un dispositivo móvil, una solicitud de tiempo de inaplicación y una programación en ukg dimensiones." lightbox="media/shifts-connector-ukg-dimensions.png":::

Los administradores de primera línea pueden:

- Publicar turnos y programaciones en dimensiones ukg y verlas en Turnos.
- Cree, vea, administre y asigne turnos abiertos en Dimensiones y turnos de UKG en el escritorio de Teams y la aplicación web de Teams. (Actualmente, los administradores no pueden ver ni asignar turnos abiertos en Turnos en dispositivos móviles de Teams).
- Cree, edite y elimine el tiempo de expiración en Las dimensiones de UKG y la vista en Desplazamientos.
- Vea y apruebe las solicitudes de programación de los trabajadores tanto en dimensiones de UKG como en turnos.
- Establezca y actualice la disponibilidad de los trabajadores en las dimensiones de UKG y la vista en turnos.

Los trabajadores de primera línea pueden:

- Ver sus turnos y horarios propios y de su equipo en Turnos.
- Solicite tiempo de descuento, vea la información de tiempo de descuento y vea los turnos abiertos de su equipo en Turnos.
- Ver y publicar entradas de tarjeta de tiempo en Turnos.
- Solicitar turnos abiertos e intercambiar turnos en Turnos.
- Establezca su disponibilidad en Turnos en dispositivos móviles de Teams.

En la actualidad, no son compatibles:

- Agregar, editar, eliminar, guardar o publicar turnos en Turnos.
- Agregar, editar, eliminar, guardar o publicar el tiempo de expiración en Turnos.
- Agregar, editar, eliminar, guardar o publicar turnos abiertos en Turnos.

Cuando un administrador o trabajador de primera línea intente realizar cualquiera de estas acciones en Turnos, recibirá un mensaje para informarles de que la acción no es compatible.

#### <a name="example-scenario"></a>Escenario de ejemplo

Ravi, un administrador, publica una programación en UKG Dimensions, que se sincroniza con Turnos en Teams a través del conector. Camille, miembro del personal, recibe una notificación en Teams en su dispositivo móvil y ve su programación y la programación de su equipo. Dentro de los turnos asignados, Camille también puede ver información detallada, como tareas, establecidas por el administrador.

Camille necesita tomarse un tiempo libre y solicita un día de descanso mediante turnos. La solicitud se envía a UKG Dimensions a través del conector. UKG Dimensions garantiza que la solicitud es compatible con las reglas de negocio y se crea la solicitud. Ravi ve y aprueba la solicitud en UkG Dimensions, y la aprobación se sincroniza con Teams. (Ravi también puede ver y aprobar la solicitud en turnos). Camille recibe una notificación en Teams de que la solicitud está aprobada y ve su programación actualizada.

Camille quiere cambiar un turno con un compañero de trabajo. En Turnos, Camille ve una lista de todos los turnos que son aptos para un intercambio basado en las reglas de negocio de UKG Dimensions. Camille elige un turno que está asignado actualmente a Kristen. Kristen recibe una notificación en Teams en su dispositivo móvil y acepta la solicitud de intercambio. Ravi ve y aprueba la solicitud en Turnos, y la aprobación se sincroniza con las dimensiones de UKG. (Ravi también puede ver y aprobar la solicitud en UKG Dimensions). Camille y Kristen reciben notificaciones en Teams y ven sus programaciones actualizadas.

#### <a name="set-up-a-connection-to-ukg-dimensions"></a>Configuración de una conexión a las dimensiones de UKG

La integración de Shifts con UKG Dimensions mediante el conector realiza solo unos pasos. Puede usar el asistente del conector Shifts en el Centro de administración de Microsoft 365 para configurar rápidamente una conexión. El asistente configura el conector en función de la configuración que elija y cree la conexión. Si prefiere usar PowerShell, también proporcionamos scripts de PowerShell que puede usar para conectarse.

Para obtener instrucciones paso a paso, consulte:

- [Uso del asistente del conector Shifts para conectar shifts a ukg dimensiones](shifts-connector-wizard-ukg.md)
- [Uso de PowerShell para conectar turnos a dimensiones de UKG](shifts-connector-ukg-powershell-setup.md)

Una vez configurada una conexión, puede actualizar y cambiar la configuración de conexión en cualquier momento, según sea necesario. Para más información, vea:

- [Use la Centro de administración de Microsoft 365 para administrar la conexión de Shifts a UKG Dimensions.](shifts-connector-ukg-admin-center-manage.md)
- [Uso de PowerShell para administrar la conexión de Shifts a UKG Dimensions](shifts-connector-ukg-powershell-manage.md)

En cuanto al conector en sí, no es necesario preocuparse por las actualizaciones o el mantenimiento. Nosotros nos encargaremos de eso.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Conector de Turnos Reflexis para Microsoft Teams

Zebra hospeda y administra el conector de Turnos Reflexis para Microsoft Teams. Con este conector, puede integrar Turnos con el sistema de WFM Reflexis para administrar las programaciones y mantenerlas actualizadas.

Los trabajadores de primera línea tienen acceso a su programación en Turnos en Teams y sus solicitudes se sincronizan desde Turnos a Reflexis Workforce Scheduler (RWS). El estado de las solicitudes y los turnos creados en RWS se sincroniza con Turnos en Teams.

:::image type="content" source="media/shifts-connector-reflexis.png" alt-text="Captura de pantalla que muestra la lista de turnos en un dispositivo móvil y una programación en Reflexis." lightbox="media/shifts-connector-reflexis.png":::

Los administradores de primera línea pueden:

- Publicar turnos y programaciones en Reflexis y verlos en Turnos.
- Editar los turnos en Reflexis y Turnos.
- Crear, administrar y asignar turnos abiertos en Reflexis y Mayús.
- Ver y aprobar las solicitudes de programación de los trabajadores en Reflexis y Shifts.

Los trabajadores de primera línea pueden:

- Ver sus turnos y horarios propios y de su equipo en Turnos.
- Solicitar tiempo libre, turnos abiertos y cambiar y ofrecer turnos en Turnos.

Para obtener más información, vaya al sitio web de <https://connect.zebra.com/microsoft-connectors>.

## <a name="related-articles"></a>Artículos relacionados

- [Administrar la aplicación Turnos para su organización en Teams](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
