---
title: Problemas conocidos del conector Team Shifts para las dimensiones de UKG
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Enumera los problemas conocidos al usar el conector Team Shifts para UKG Dimensions para integrar Shifts con UKG Dimensions.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 10c1f0aff03fb302cc12cae78cf003d2f337a01a
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68234563"
---
# <a name="known-issues-team-shifts-connector-for-ukg-dimensions"></a>Problemas conocidos: Conector de turnos de equipo para dimensiones ukg

[!INCLUDE [preview-feature](includes/preview-feature.md)]

En este artículo se enumeran los problemas [conocidos del conector turnos de Microsoft Teams para dimensiones UKG](shifts-connectors.md#microsoft-teams-shifts-connector-for-ukg-dimensions).

## <a name="you-can-map-an-instance-to-more-than-one-team-using-powershell-or-microsoft-graph"></a>Puede asignar una instancia a más de un equipo mediante PowerShell o Microsoft Graph

Una instancia de UKG Dimensions solo debe asignarse a un equipo en un momento dado en una conexión.

Sin embargo, cuando se usa PowerShell o Microsoft Graph para configurar una conexión, es posible asignar una instancia a más de un equipo. Se recomienda evitar la asignación de una instancia a varios equipos, ya que puede dar lugar a problemas de sincronización y comportamientos inesperados.

## <a name="frontline-managers-can-select-a-time-zone-for-a-schedule-in-shifts-thats-different-from-the-time-zone-thats-set-in-ukg-dimensions"></a>Los administradores de primera línea pueden seleccionar una zona horaria para una programación en Turnos que sea diferente de la zona horaria establecida en Dimensiones de UKG.

La configuración de zona horaria de las programaciones en Turnos se sincroniza desde dimensiones ukg. Sin embargo, es posible que los administradores de primera línea cambien la zona horaria de una programación en Turnos a una que sea diferente de la configurada en Dimensiones de UKG. Esto puede dar lugar a problemas de sincronización y comportamiento inesperado.

Para solucionar este problema, mantenga la configuración de zona horaria tal y como está.

## <a name="nothing-happens-when-users-select-the-start-a-break-and-end-break-buttons-in-shifts-to-start-or-end-a-break"></a>No ocurre nada cuando los usuarios seleccionan los botones "Iniciar una interrupción" y "Finalizar interrupción" en Turnos para iniciar o finalizar una interrupción

La funcionalidad de interrupción de inicio y finalización de la característica de reloj de hora no se admite en una integración con ukg dimensiones. Los usuarios no podrán sacar el reloj ni reloj en un salto, aunque los botones se muestren en Turnos.

## <a name="a-user-cant-perform-some-actions-in-shifts-in-the-teams-web-app-after-signing-in-with-a-different-account"></a>Un usuario no puede realizar algunas acciones en Turnos en la aplicación web de Teams después de iniciar sesión con una cuenta diferente

Este problema puede producirse si un usuario que tiene varias cuentas en Teams realiza acciones en Turnos que requieren inicio de sesión único (SSO) en UKG Dimensions y ese usuario cambia de cuenta en la aplicación web de Teams en el mismo explorador.

Por ejemplo, un usuario inicia sesión en Teams, aprueba una solicitud de tiempo de espera y, a continuación, cierra la sesión. A continuación, el usuario inicia sesión en Teams con una cuenta diferente e intenta realizar otra acción en Shifts que requiere el inicio de sesión único en UKG Dimensions.

En este escenario, se produce un problema de almacenamiento en caché en el que el usuario inicia sesión en Teams y cambia en una cuenta e inicia sesión en UKG Dimensions en la otra cuenta.

Como solución alternativa a este problema, siga uno de estos procedimientos:

- Borrar las cookies y los datos del sitio para el sitio mykronos.com en el explorador. Para más información, consulte [Eliminación de cookies en Microsoft Edge](https://support.microsoft.com/microsoft-edge/delete-cookies-in-microsoft-edge-63947406-40ac-c3b8-57b9-2a946a29ae09) o [Borrar, habilitar y administrar cookies en Chrome](https://support.google.com/chrome/answer/95647).
- Use la aplicación web de Teams en una ventana de InPrivate en Microsoft Edge o en modo incógnito en Google Chrome.

## <a name="related-articles"></a>Artículos relacionados

- [Conectores de Turnos](shifts-connectors.md)
- [Uso del asistente del conector Shifts para conectar shifts a ukg dimensiones](shifts-connector-wizard-ukg.md)
- [Uso de PowerShell para conectar turnos a dimensiones de UKG](shifts-connector-ukg-powershell-setup.md)
- [Use la Centro de administración de Microsoft 365 para administrar la conexión de Shifts a UKG Dimensions.](shifts-connector-ukg-admin-center-manage.md)
- [Uso de PowerShell para administrar la conexión de Shifts a UKG Dimensions](shifts-connector-ukg-powershell-manage.md)
- [Administrar la aplicación Turnos para su organización en Teams](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
