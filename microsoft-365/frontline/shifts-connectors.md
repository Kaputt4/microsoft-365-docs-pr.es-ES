---
title: Conectores de Turnos
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Obtenga información sobre los conectores de turnos y cómo usarlos para conectar turnos a su sistema de administración de personal.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: c211e066a1b5c6ad610c2f3be703d50be3ecf6af
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "66998672"
---
# <a name="shifts-connectors"></a>Conectores de Turnos

## <a name="overview"></a>Información general

Los conectores de turnos le permiten integrar Turnos, la herramienta de administración de programaciones en Microsoft Teams, con el sistema de administración de personal (workforce management, WFM). Después de configurar una conexión, los trabajadores de primera línea pueden ver y administrar sin problemas sus programaciones en Blue Yonder WFM desde Turnos.

La conexión del sistema de WFM a Teams permite a los empleados de primera línea administrar programaciones de forma más eficaz y simplifica los procesos diarios para lograr una mayor participación y productividad. Los trabajadores de primera línea tienen un lugar para que su programación, comunicación y colaboración tengan que realizar el trabajo, desde cualquier lugar y en cualquier dispositivo.

En este artículo se proporciona información general sobre los conectores de turnos y cómo funcionan.

## <a name="how-shifts-connectors-work"></a>Funcionamiento de los conectores de turnos

Los conectores sincronizan los datos de programación entre el sistema de WFM y los turnos, lo que lleva las programaciones de la organización a Teams. Los turnos son los lugares en los que los trabajadores de primera línea se involucran para sus necesidades de programación. El sistema de WFM es el sistema de registro de reglas de negocio, cumplimiento e inteligencia.

Los flujos de datos a través del conector garantizan que las programaciones estén siempre actualizadas. Las programaciones del sistema de WFM se sincronizan con Turnos. Además, los cambios realizados en las programaciones de Turnos se sincronizan de nuevo con el sistema de WFM en tiempo real. Como sistema de registro, el sistema de WFM aplica todas las reglas de negocio antes de que los datos se guarden en Turnos.

## <a name="managed-shifts-connectors"></a>Conectores de turnos administrados

Los conectores de Turnos administrados son conectores desarrollados en colaboración con nuestros asociados. Los conectores administrados están hospedados y administrados por nosotros o nuestros asociados. Con los conectores administrados, solo se necesita una configuración mínima.

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Conector de turnos de Microsoft Teams para Blue Yonder
<a name="blue_yonder"> </a>

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

Alex necesita coger tiempo libre y solicita un día libre mediante Turnos. La solicitud se envía a Blue Yonder WFM a través del conector en tiempo real. Blue Yonder WFM garantiza que la solicitud es compatible con las reglas de negocio y se crea la solicitud. Eden ve y aprueba la solicitud en Blue Yonder WFM y la aprobación se sincroniza con Teams. (Eden también puede ver y aprobar la solicitud en Turnos). Alex recibe una notificación en Teams de que su solicitud está aprobada y ve su programación actualizada.

Alex quiere cambiar un turno con un compañero de trabajo. En Turnos, Alex ve una lista de todos los turnos que son aptos para un intercambio basado en las reglas de negocio en Blue Yonder WFM. Alex elige un turno que está asignado actualmente a Gena. Gena recibe una notificación en Teams en su dispositivo móvil y acepta la solicitud de intercambio. Eden ve y aprueba la solicitud en Turnos, y la aprobación se sincroniza con Blue Yonder WFM. (Eden también puede ver y aprobar la solicitud en Blue Yonder WFM). Alex y Gena reciben una notificación en Teams y ven sus programaciones actualizadas.

#### <a name="set-up-a-connection"></a>Configuración de una conexión

La integración de Shifts con Blue Yonder WFM mediante el conector se realiza en solo unos pasos. Puede usar el asistente del conector Shifts en el Centro de administración de Microsoft 365 para configurar rápidamente una conexión. El asistente configura el conector en función de la configuración que elija y cree la conexión. Si prefiere usar PowerShell, también proporcionamos scripts de PowerShell que puede usar para conectarse.

Para obtener instrucciones paso a paso, consulte:

- [Use el asistente del conector de Turnos para conectar Turnos a Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [Uso de PowerShell para conectar Turnos a Workforce Management de Blue Yonder](shifts-connector-blue-yonder-powershell-setup.md)

Una vez configurada una conexión, puede usar PowerShell para actualizar y cambiar la configuración de conexión en cualquier momento, según sea necesario. En cuanto al conector en sí, no es necesario preocuparse por las actualizaciones o el mantenimiento. Nosotros nos encargaremos de eso.

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

Para obtener más información, vaya al sitio web de https://connect.zebra.com/microsoft-connectors.

## <a name="related-articles"></a>Artículos relacionados

- [Administrar la aplicación Turnos para su organización en Teams](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
