---
title: Configurar auditoría básica en Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: En este artículo se describe cómo configurar auditoría básica para que pueda empezar a buscar actividades de auditoría realizadas por usuarios y administradores de la organización.
ms.openlocfilehash: 59b5c85003ef0e19f7d3dd7417f764f446244652
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52564834"
---
# <a name="set-up-basic-audit-in-microsoft-365"></a>Configurar auditoría básica en Microsoft 365

Auditoría básica en Microsoft 365 le permite buscar registros de auditoría para las actividades realizadas en los diferentes servicios de Microsoft 365 por usuarios y administradores. Dado que la auditoría básica está habilitada de forma predeterminada para la mayoría de las organizaciones Microsoft 365 y Office 365, solo hay algunas cosas que debe hacer antes de que usted y otros miembros de la organización puedan buscar en el registro de auditoría.

En este artículo se describen los pasos siguientes necesarios para configurar la auditoría básica.

![Pasos para configurar la Auditoría Básica](../media/BasicAuditingWorkflow.png)

Estos pasos incluyen garantizar las suscripciones organizativas adecuadas y las licencias de usuario necesarias para generar y conservar registros de auditoría y asignar permisos a los miembros del equipo de sus operaciones de seguridad, TI, cumplimiento y equipos legales para que puedan buscar en el registro de auditoría.

Para obtener más información, consulte [Auditoría básica en Microsoft 365](auditing-solutions-overview.md#basic-audit).

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a>Paso 1: Verifique la suscripción de la organización y las licencias de usuario

Las licencias para auditoría básica requieren la suscripción de organización adecuada que proporciona acceso a la herramienta de búsqueda de registros de auditoría y a las licencias por usuario necesarias para registrar y conservar registros de auditoría.

Cuando un usuario o administrador realiza una actividad auditada, se genera un registro de auditoría y se almacena en el registro de auditoría de la organización. En Auditoría básica, los registros de auditoría se conservan y se pueden buscar en el registro de auditoría durante 90 días.

Para obtener una lista de los requisitos de suscripción y licencias para auditoría básica, consulte [Soluciones de auditoría en Microsoft 365](auditing-solutions-overview.md#licensing-requirements).

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a>Paso 2: Asignar permisos para buscar en el registro de auditoría

A los administradores y miembros de los equipos de investigación se les debe asignar el rol registros de auditoría o registros de auditoría View-Only en Exchange Online para buscar en el registro de auditoría. De forma predeterminada, estos roles se asignan a los grupos de roles de Administración de la organización y Administración de cumplimiento en la página de **permisos** del centro de administración de Exchange. Los administradores globales de Office 365 y Microsoft 365 se agregan automáticamente como miembros del grupo de roles Administración de la organización en Exchange Online. Para darle a un usuario la capacidad de buscar en el registro de auditoría con el mínimo nivel de privilegios, puede crear un grupo de roles personalizado en Exchange Online, agregar el rol de Registros de auditoría o Registros de auditoría de solo lectura y, después, agregar el usuario como miembro del nuevo grupo de roles. Para obtener más información, consulte[Administrar grupos de roles en Exchange en línea](/Exchange/permissions-exo/role-groups).

En la siguiente captura de pantalla se muestran los dos roles relacionados con auditoría asignados al grupo de roles Administración de la organización en el centro de administración de Exchange.

![Roles de auditoría asignados al grupo de roles en Exchange Online](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a>Paso 3: Busque en el registro de auditoría

Ahora está listo para buscar en el registro de auditoría en el centro de cumplimiento de Microsoft 365.

1. Vaya <https://compliance.microsoft.com> e inicie sesión con una cuenta a la que se le han asignado los permisos de auditoría adecuados.

2. En el panel de navegación izquierdo del centro de cumplimiento de Microsoft 365, haga clic en **Mostrar todo** y, a continuación, haga clic en **Auditoría**.

3. En la página **Auditoría,** configure la búsqueda mediante las siguientes condiciones en la pestaña **Buscar.** 

   ![Configuración para la búsqueda de registros de auditoría](../media/AuditLogSearchToolMCCCallouts.png)

   1. **Fecha y intervalo de tiempo.** Seleccione un intervalo de fecha y hora para mostrar los eventos que han sucedido en ese período. La fecha y la hora se muestran en hora local. Los últimos siete días se seleccionan de forma predeterminada.
  
   2. **Actividades**. Seleccione las actividades que desea buscar. Utilice el cuadro de búsqueda para buscar actividades que agregar a la lista. Para obtener una lista parcial de las actividades auditadas, consulte [Actividades auditadas](search-the-audit-log-in-security-and-compliance.md#audited-activities). Deje este cuadro en blanco para devolver entradas para todas las actividades auditadas.
  
   3. Usuarios  Haga clic en este cuadro y comience a escribir el nombre de los usuarios para los que mostrar los resultados de búsqueda. Las entradas de registro de auditoría para las actividades seleccionadas realizadas por los usuarios seleccionados en este cuadro se muestran en la lista de resultados. Deje este cuadro en blanco para devolver las entradas de todos los usuarios (y cuentas de servicio) de su organización.
  
   4. **Archivo, carpeta o sitio**. Escriba parte o la totalidad de un nombre de archivo o carpeta para buscar actividad relacionada con el archivo de carpeta que contiene la palabra clave especificada. También puede especificar una dirección URL de un archivo o carpeta. Si utiliza una dirección URL de un archivo o carpeta, asegúrese de que escriba la ruta de URL completa o si escribe una parte de la dirección URL, no incluya caracteres o espacios especiales. Deje este cuadro en blanco para devolver las entradas de todos los archivos y carpetas de la organización.

4. Haga clic en **Buscar** para ejecutar la búsqueda.

Se muestra una nueva página que muestra la búsqueda del registro de auditoría en ejecución. Cuando se completa la búsqueda, los registros de auditoría se muestran en la página. Haga clic en un registro para mostrar una página desplegable con propiedades detalladas.

Para obtener instrucciones más detalladas, consulte [Buscar en el registro de auditoría en el centro de cumplimiento.](search-the-audit-log-in-security-and-compliance.md)
