---
title: Turnos para trabajadores de primera línea
description: Obtenga la guía de administración que necesita para configurar y administrar Turnos, la herramienta de administración de programación, en Microsoft Teams.
ms.topic: conceptual
author: LanaChin
ms.author: v-lanachin
audience: admin
manager: samanro
f1.keywords:
- NOCSH
ms.service: microsoft-365-frontline
ms.collection:
- M365-collaboration
- m365-frontline
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-frontline
- m365solution-scenario
search.appverid: MET150
ms.localizationpriority: high
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: ce2c8da70b2fa6908518fc2f7d9489a2fdf578cd
ms.sourcegitcommit: 7374c7b013890744d74e5214f7f8d69ca7874466
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "67405736"
---
# <a name="shifts-for-frontline-workers"></a>Turnos para trabajadores de primera línea

Turnos, la herramienta de administración de programación de Teams, mantiene a los empleados de primera línea conectados y sincronizados. Se ha creado en primer lugar para la administración de programación y para comunicaciones rápidas y eficaces. Con Turnos, los administradores de primera línea y los trabajadores pueden administrar sin fisuras las programaciones y mantenerse en contacto.

Los administradores pueden crear, actualizar y administrar programaciones de turnos para sus equipos. Pueden asignar turnos, agregar turnos abiertos y aprobar solicitudes de programación de los empleados. Los empleados pueden ver sus propias programaciones y las de su equipo, establecer su disponibilidad, solicitar intercambiar u ofrecer un turno, solicitar permisos y marcar la entrada y la salida.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE42FjP]

Use los siguientes recursos para ayudarse a configurar y administrar turnos en su organización.

## <a name="set-up-and-manage-shifts"></a>Configurar y administrar turnos

|&nbsp;  |&nbsp; |
|---------|---------|
|<img src="/office/media/icons/calendar-teams.png" alt="Calendar symbol.">   |**[Administrar turnos](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)** Obtenga información general sobre cómo administrar turnos para su organización. Obtenga información sobre cómo controlar el acceso a turnos, anclar turnos a la barra de aplicaciones de Teams para facilitar el acceso, habilitar etiquetas basadas en turnos, etc. |
|<img src="/office/media/icons/users-people.png" alt="Users/people symbol.">   |**[Administrar propietarios de programación para la administración de turnos](schedule-owner-for-shift-management.md)** Esta característica le permite elevar los permisos de un miembro del equipo a un propietario de programación sin convertir al empleado en propietario del equipo.         |
|<img src="/office/media/icons/help.png" alt="Help symbol.">     | **[Preguntas más frecuentes sobre datos de turnos](/microsoftteams/expand-teams-across-your-org/shifts/shifts-data-faq?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)** Obtenga información sobre dónde se almacenan los datos de Turnos y otros temas relacionados con los datos de Turnos, lo que incluye retención, recuperación y cifrado.        |

## <a name="shifts-connectors"></a>Conectores de Turnos

Si usa un sistema de administración de recursos de terceros (WFM) para la programación, puede integrarlo directamente con Turnos a través de conectores de Turnos administrados. Después de configurar una conexión, los trabajadores de primera línea pueden ver y administrar sin problemas sus programaciones en Blue Yonder WFM desde Turnos.

|&nbsp;  |&nbsp;  |
|---------|---------|
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Introducción a los conectores de Turnos](shifts-connectors.md)** Obtenga información general sobre los conectores de Turnos y sobre cómo funcionan. Obtenga información sobre los conectores administrados que están disponibles y los sistemas WFM compatibles.   |
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Conectores de Turnos administrados](shifts-connectors.md#managed-shifts-connectors)** Los conectores de Turnos administrados, desarrollados en colaboración con nuestros asociados, están hospedados y administrados por nosotros o por nuestros asociados. Para obtener más información, consulte el [Conector de Turnos de Microsoft Teams para el Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) y [Conector de Turnos Reflexis para Microsoft Teams](shifts-connectors.md#reflexis-shifts-connector-for-microsoft-teams).    |
|   | **[Usar el asistente del conector de Turnos para conectar Shifts a Blue Yonder Workforce Management](shifts-connector-wizard.md)** El Asistente para conectores de Turnos del Centro de administración de Microsoft 365 le ayuda a configurar rápidamente una conexión con el sistema WFM. Actualmente, el asistente admite el conector de Turnos de Teams para Blue Yonder para integrar Shifts con Blue Yonder Workforce Management.
|  | **[Uso de PowerShell para conectar Turnos a Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)** Obtenga información sobre cómo usar PowerShell para configurar una conexión a Blue Yonder Workforce Management a través del conector de Turnos de Teams para Blue Yonder.         |
|   | **[Uso de PowerShell para administrar la conexión de Turnos a Blue Yonder Workforce Management](shifts-connector-powershell-manage.md)** Obtenga instrucciones sobre cómo usar PowerShell para administrar la conexión de Turnos a Blue Yonder Workforce Management después de configurarla mediante el Asistente para conectores de Turnos o PowerShell.

## <a name="shifts-extensions"></a>Extensiones de turnos

|&nbsp;|&nbsp;|
| ------------- | ------------- |
| <img src="/office/media/icons/api.png" alt="Three gears - API."> | **[API de Shift Graph](/graph/api/resources/shift)** Las API de Shift Graph permiten integrar los datos de Turnos con sistemas WFM externos. Tendrá la flexibilidad de crear experiencias personalizadas en Turnos en el back-end, a la vez que proporciona a los usuarios una experiencia front-end enriquecida en Teams.             |
|<img src="/office/media/icons/process-flow-teams.png" alt="Process/flow chart symbol."> | **[Turnos + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Turnos + Power Automate te permite tomar información de Turnos y crear flujos de trabajo personalizados con otras aplicaciones y realizar operaciones a escala. Automatice los procesos clave con escaso o ningún código. Los desencadenadores y las plantillas admiten varios escenarios, como es habilitar aprobaciones automáticas para las solicitudes de turno cuando no se necesita la aprobación de un administrador’. |

## <a name="featured-training"></a>Formación destacada

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| <img src="/office/media/icons/get-started-teams.png" alt="Get started symbol.">  |  [Vídeo: ¿Qué es Turnos?](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |<img src="/office/media/icons/clock-teams.png" alt="Clock symbol."> |  [Vídeo: Crear una programación de turnos](https://support.microsoft.com/office/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |<img src="/office/media/icons/blocks-teams.png" alt="Blocks symbol.">|  [Vídeo: Administrar una programación de turnos](https://support.microsoft.com/office/manage-and-view-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
