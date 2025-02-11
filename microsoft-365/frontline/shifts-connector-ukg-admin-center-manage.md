---
title: Use la Centro de administración de Microsoft 365 para administrar la conexión de Shifts a UKG Dimensions.
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: how-to
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Obtenga información sobre cómo administrar la conexión de Shifts a UKG Dimensions en el Centro de administración de Microsoft 365.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 0c02385cf3733f9daf2c1e24db244e3b78afd069
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2022
ms.locfileid: "68786019"
---
# <a name="use-the-microsoft-365-admin-center-to-manage-your-shifts-connection-to-ukg-dimensions"></a>Use la Centro de administración de Microsoft 365 para administrar la conexión de Shifts a UKG Dimensions.

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Información general

El [conector Turnos de Microsoft Teams para ukg dimensiones](shifts-connectors.md#microsoft-teams-shifts-connector-for-ukg-dimensions) permite integrar la aplicación Shifts en Microsoft Teams con UKG Dimensions. Después de configurar una conexión, los trabajadores de primera línea pueden ver y administrar sin problemas sus programaciones en las dimensiones de UKG desde los turnos.

Puede usar el [asistente del conector Shifts](shifts-connector-wizard-ukg.md) en el Centro de administración de Microsoft 365 o [PowerShell](shifts-connector-ukg-powershell-setup.md) para crear una conexión. Una vez configurada una conexión, puede administrarla en el Centro de administración de Microsoft 365. La página Administración de conectores muestra cada conexión que ha configurado, junto con información como el estado de mantenimiento y los detalles del intervalo de sincronización. También puede acceder al asistente para crear una nueva conexión o realizar cambios en cualquiera de las conexiones existentes. Por ejemplo, puede actualizar la configuración de sincronización y las asignaciones de equipo.

> [!NOTE]
> También puede usar PowerShell para administrar una conexión. Por ejemplo, puede ver un informe de errores, cambiar la configuración de conexión y deshabilitar la sincronización. Para más información, consulte [Uso de PowerShell para administrar la conexión shifts a las dimensiones de UKG](shifts-connector-ukg-powershell-manage.md).

## <a name="manage-your-connection"></a>Administrar la conexión

1. En el panel de navegación izquierdo de la [Centro de administración de Microsoft 365](https://admin.microsoft.com/), elija **Configurar** y, a continuación, en **Colecciones destacadas**, seleccione **Trabajos de primera línea**.
2. Seleccione **Administrar conectores de turnos** y, a continuación, elija **Administrar**. Tenga en cuenta que esta opción solo está disponible si ha configurado al menos una conexión, ya sea mediante el asistente o PowerShell.

    Aquí verá una lista de todas las conexiones que ha configurado a través del asistente o PowerShell, junto con información sobre cada una de ellas.

    :::image type="content" source="media/shifts-connector-ukg-manage.png" alt-text="Captura de pantalla de la página Administración de conectores de la Centro de administración de Microsoft 365, en la que se muestra una lista de conexiones." lightbox="media/shifts-connector-ukg-manage.png":::

    - Para crear una nueva conexión, seleccione **Agregar conector** en la parte superior de la página para iniciar el asistente.

    - Para ver más detalles sobre una conexión, haga clic en el nombre de la conexión. En la página de detalles, verá información de estado, incluidos errores de autorización de cuenta y asignación (si los hubiera), la lista de asignaciones (si existe) y mucho más. También puede elegir **Editar** para actualizar la configuración de conexión en el asistente.

      :::image type="content" source="media/shifts-connector-ukg-manage-details.png" alt-text="Captura de pantalla de la página de detalles de una conexión, en la que se muestra información sobre el estado y las asignaciones del conector." lightbox="media/shifts-connector-ukg-manage-details.png":::

         Para obtener una lista completa de los mensajes de error y cómo resolverlos, consulte [Lista de mensajes de error](#list-of-error-messages) más adelante en este artículo.

    - Para realizar cambios en una conexión, elija **Editar** junto a la conexión. Se le llevará al asistente, donde podrá actualizar la configuración que desee.
  
> [!NOTE]
> También puede ir directamente a la página Administración de conectores cuando seleccione el botón **Administración de conectores** en la última página del asistente durante la instalación de la conexión.

## <a name="list-of-error-messages"></a>Lista de mensajes de error

Esta es la lista de mensajes de error que puede encontrar e información para ayudarle a resolverlos.

|Tipo de error |Detalles del error |Solución |
|---------|---------|---------|
|No se puede autenticar el sistema de administración de la fuerza de trabajo.|Las credenciales de la cuenta del sistema de administración del personal que ha proporcionado no son válidas o esta cuenta no tiene los permisos necesarios.|Actualice las credenciales de la cuenta de servicio de WFM en la configuración de conexión. Para ello, siga uno de estos procedimientos:<ul><li>En el Centro de administración de Microsoft 365, elija **Editar** en la página Administración de conectores o en la página de detalles de conexión para ir al Asistente para conectores de turnos.</li><li>Use el cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) o [Update-CsTeamsShiftsConnectionInstance](/powershell/module/teams/update-csteamsshiftsconnectioninstance) .</li><li>Use [este script de PowerShell](shifts-connector-ukg-powershell-manage.md#change-connection-settings).</li></ul>|
|No se puede autenticar Graph. |Error de autenticación. Asegúrese de que ha escrito credenciales válidas para el actor designado y que tiene los permisos necesarios.|Asegúrese de que la cuenta del sistema de Microsoft 365 (también conocida como actor designado) se agrega como propietario del equipo.<br> O bien, actualice las credenciales de la cuenta del sistema de Microsoft 365 en la configuración de conexión.|
|Algunos usuarios no se han asignado correctamente|Error en la asignación de algunos usuarios: \<X\> usuarios de AAD correctos, \<X\> con errores y \<X\> usuarios del sistema de administración de fuerza de trabajo con errores.|Use el cmdlet [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult) o [este script de PowerShell](shifts-connector-ukg-powershell-manage.md#user-mapping-errors) para identificar a los usuarios para los que se produjo un error en la asignación. Asegúrese de que los usuarios del equipo asignado coincidan con los usuarios de la instancia de WFM.|
|No se puede asignar un equipo o equipos en este lote. |Este perfil de actor designado no tiene privilegios de propiedad de equipo. |Asegúrese de que la cuenta del sistema de Microsoft 365 (también conocida como actor designado) se agrega como propietario del equipo.<br>Si ha cambiado la cuenta del sistema de Microsoft 365, agregue esa cuenta como propietario del equipo y actualice la configuración de conexión para usarla.|
|    |Este equipo ya está asignado a una instancia de conector existente. |Quite la asignación del equipo de la conexión existente mediante el cmdlet [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap) . O bien, cree una nueva conexión para volver a asignar el equipo.|
|    |Esta zona horaria no es válida. La zona horaria pasada no usa el formato de base de datos tz.|Asegúrese de que la zona horaria es correcta y, a continuación, vuelva a asignar el equipo.|
|    |No podemos encontrar esta instancia del conector.|Asigne el equipo a una conexión existente.|
|    |No se encontró este equipo de AAD.|Asegúrese de que el equipo existe o cree un nuevo equipo.|

## <a name="related-articles"></a>Artículos relacionados

- [Conectores de Turnos](shifts-connectors.md)
- [Uso del asistente del conector Shifts para conectar shifts a ukg dimensiones](shifts-connector-wizard-ukg.md)
- [Uso de PowerShell para conectar turnos a dimensiones de UKG](shifts-connector-ukg-powershell-setup.md)
- [Uso de PowerShell para administrar la conexión de Shifts a UKG Dimensions](shifts-connector-ukg-powershell-manage.md)
- [Administrar la aplicación Turnos para su organización en Teams](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
