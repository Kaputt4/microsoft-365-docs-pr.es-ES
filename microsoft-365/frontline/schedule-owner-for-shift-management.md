---
title: Administrar propietarios de programación para la administración de turnos
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
description: Obtenga información sobre cómo administrar propietarios de turnos para la administración de programaciones. Puede establecer una directiva para elevar el permiso de un miembro del equipo a un propietario de programación.
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
- microsoftcloud-healthcare
- microsoftcloud-retail
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7e91519820adbefd780f27759c3da4ef31d7cb8f
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "66998588"
---
# <a name="schedule-owner-for-shift-management"></a>Programar propietario para la administración de turnos

## <a name="overview"></a>Información general

La característica Propietario de programación le permite elevar los permisos de un miembro del equipo para que pueda administrar las programaciones sin convertir al empleado en propietario del equipo. Con los permisos de Propietario de programación, un empleado puede administrar la programación de su equipo sin poder modificar otras propiedades del equipo, como actualizar, editar o eliminar canales de equipo.

¿Qué puede hacer un usuario con permisos de propietario de programación?

- Crear, editar y publicar programaciones para administrar las asignaciones de turnos de su equipo.
- Ver y aprobar solicitudes de turnos, incluidas las solicitudes para intercambiar turnos y realizar turnos abiertos.
- Administrar la configuración en Turnos para habilitar determinadas características para el equipo.
- Ver y modificar el parte de horas de su equipo para procesar las nóminas de los empleados.

## <a name="why-schedule-owner"></a>¿Por qué Propietario de programación?

Sin la característica Propietario de programación, se podrían interrumpir las funciones empresariales diarias. Aunque el propietario del equipo ayuda a dirigir el equipo, es posible que no sea necesariamente la persona responsable de la programación diaria. En este caso, transferir solo la responsabilidad de administración de programación a otro miembro del equipo simplifica las operaciones diarias dentro del equipo y elimina la confusión de dos miembros del equipo que tienen los mismos privilegios de acceso.

## <a name="scenario"></a>Escenario

Este es un ejemplo de cómo su organización puede usar la característica Propietario de programación.

Trabaja en una organización grande en la que los jefes de departamento informan directamente al administrador de la tienda. El administrador de la tienda tiene más autoridad dentro de su empresa y es el propietario del equipo en Turnos. Por otro lado, los jefes de departamento solo se agregan a Turnos como miembros del equipo. Aunque los administradores de tiendas tienen más antigüedad que los jefes de departamento, tiene más sentido que los jefes de departamento controlen la programación diaria de los empleados de su equipo.

*Sin Propietario de la programación*, los administradores de departamento deben tener exactamente los mismos privilegios que el propietario del equipo. Recientemente, los jefes de departamento han estado moviendo la información y cambiando el nombre de los canales, lo que ha provocado complicaciones con el trabajo del administrador de la tienda. El administrador de la tienda quiere que los jefes de departamento puedan organizar sus programaciones, pero no quiere que puedan cambiar nada más en el equipo, fuera de Turnos.

*Con Propietario de la programación*, se pueden conceder privilegios de programación a los administradores de departamento, sin ningún otro privilegio de propietario del equipo.

## <a name="manage-schedule-ownership"></a>Administrar la propiedad de la programación

Como administrador, puede usar directivas para controlar la propiedad de la administración de programación en su organización. Estas directivas se administran mediante los siguientes cmdlets de PowerShell:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy?view=teams-ps)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy?view=teams-ps)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy?view=teams-ps)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy?view=teams-ps)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy?view=teams-ps)

### <a name="example-1"></a>Ejemplo 1

Aquí, creamos una nueva directiva denominada ScheduleOwnerPolicy con la característica Propietario de programación activada.

```powershell
New-CsTeamsShiftsPolicy –Identity ScheduleOwnerPolicy  -EnableScheduleOwnerPermissions $true -AccessType UnrestrictedAccess_TeamsApp
```

### <a name="example-2"></a>Ejemplo 2

En este ejemplo, asignamos una directiva denominada ScheduleOwnerPolicy a un usuario denominado remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName ScheduleOwnerPolicy
```

## <a name="related-articles"></a>Artículos relacionados

- [Administrar la aplicación Turnos para su organización en Teams](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Administrar el acceso basado en turnos para los trabajadores de primera línea en Teams](manage-shift-based-access-flw.md)
