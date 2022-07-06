---
title: Configuración de auditoría (estándar) en Microsoft 365
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
ms.custom: admindeeplinkEXCHANGE
search.appverid:
- MOE150
- MET150
description: En este artículo se describe cómo configurar auditoría (estándar) para que pueda empezar a buscar actividades de auditoría realizadas por usuarios y administradores de su organización.
ms.openlocfilehash: 17f9e24f4c3159186011d3faefbd8796f51cc5ce
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66632209"
---
# <a name="set-up-microsoft-purview-audit-standard"></a>Configurar Auditoría de Microsoft Purview (estándar)

Auditoría de Microsoft Purview (Estándar) en Microsoft 365 permite buscar registros de auditoría para las actividades realizadas en los distintos servicios de Microsoft 365 por parte de usuarios y administradores. Dado que La auditoría (estándar) está habilitada de forma predeterminada para la mayoría de las organizaciones de Microsoft 365 y Office 365, solo hay algunas cosas que debe hacer antes de que usted y otros usuarios de su organización puedan buscar en el registro de auditoría.

En este artículo se describen los pasos siguientes necesarios para configurar auditar (estándar).

![Pasos para configurar auditoría (estándar).](../media/BasicAuditingWorkflow.png)

Estos pasos incluyen garantizar las suscripciones de la organización y las licencias de usuario adecuadas necesarias para generar y conservar registros de auditoría y asignar permisos a los miembros del equipo de operaciones de seguridad, TI, cumplimiento y equipos legales para que puedan buscar en el registro de auditoría.

Para obtener más información, consulte [Auditoría (estándar) en Microsoft 365](auditing-solutions-overview.md#audit-standard).

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a>Paso 1: Comprobar la suscripción de la organización y las licencias de usuario

Licencias para auditoría (estándar) requiere la suscripción de organización adecuada que proporciona acceso a la herramienta de búsqueda de registros de auditoría y a las licencias por usuario necesarias para registrar y conservar registros de auditoría.

Cuando un usuario o administrador realiza una actividad auditada, se genera un registro de auditoría y se almacena en el registro de auditoría de la organización. En Auditoría (estándar), los registros de auditoría se conservan y se pueden buscar en el registro de auditoría durante 90 días.

Para obtener una lista de los requisitos de suscripción y licencia para auditoría (estándar), consulte [Soluciones de auditoría en Microsoft 365](auditing-solutions-overview.md#licensing-requirements).

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a>Paso 2: Asignar permisos para buscar en el registro de auditoría

A los administradores y miembros de los equipos de investigación se les debe asignar el rol View-Only Registros de auditoría o Registros de auditoría en Exchange Online para buscar en el registro de auditoría. De forma predeterminada, estos roles se asignan a los grupos de roles de Administración de la organización y Administración de cumplimiento en la página de **Permisos** del <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>. Los administradores globales de Office 365 y Microsoft 365 se agregan automáticamente como miembros del grupo de roles de administración de la organización en Exchange Online. Para darle a un usuario la capacidad de buscar en el registro de auditoría con el mínimo nivel de privilegios, puede crear un grupo de roles personalizado en Exchange Online, agregar el rol de Registros de auditoría o Registros de auditoría de solo lectura y, después, agregar el usuario como miembro del nuevo grupo de roles. Para obtener más información, consulte[Administrar grupos de roles en Exchange en línea](/Exchange/permissions-exo/role-groups).

En la captura de pantalla siguiente se muestran los dos roles relacionados con la auditoría asignados al grupo de roles Administración de la organización en el Centro de administración de Exchange.

![Audite los roles asignados al grupo de roles en Exchange Online.](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a>Paso 3: Buscar en el registro de auditoría

Ahora está listo para buscar en el registro de auditoría en el portal de cumplimiento Microsoft Purview.

1. Vaya a <https://compliance.microsoft.com> e inicie sesión con una cuenta a la que se hayan asignado los permisos de auditoría adecuados.

2. En el panel de navegación izquierdo del portal de cumplimiento, haga clic en **Mostrar todo** y, a continuación, haga clic en **Auditar**.

3. En la página **Auditoría** , configure la búsqueda con las siguientes condiciones en la pestaña **Buscar** . 

   ![Opciones de configuración para la búsqueda de registros de auditoría.](../media/AuditLogSearchToolMCCCallouts.png)

   1. **Intervalo de fecha y hora**. Seleccione un intervalo de fecha y hora para mostrar los eventos que han sucedido en ese período. La fecha y la hora se muestran en hora local. Los últimos siete días se seleccionan de forma predeterminada.
  
   2. **Actividades**. Seleccione las actividades que desea buscar. Use el cuadro de búsqueda para buscar las actividades que se van a agregar a la lista. Para obtener una lista parcial de las actividades auditadas, consulte [Actividades auditadas](search-the-audit-log-in-security-and-compliance.md#audited-activities). Deje este cuadro en blanco para devolver entradas para todas las actividades auditadas.
  
   3. Usuarios  Haga clic en este cuadro y empiece a escribir el nombre de los usuarios para mostrar los resultados de la búsqueda. Las entradas del registro de auditoría de las actividades seleccionadas realizadas por los usuarios que seleccione en este cuadro se muestran en la lista de resultados. Deje este cuadro en blanco para devolver las entradas de todos los usuarios (y cuentas de servicio) de su organización.
  
   4. **Archivo, carpeta o sitio**. Escriba algunos o todos los nombres de archivo o carpeta para buscar la actividad relacionada con el archivo de carpeta que contiene la palabra clave especificada. También puede especificar una dirección URL de un archivo o carpeta. Si usa una dirección URL de un archivo o carpeta, asegúrese de que escriba la ruta de acceso de dirección URL completa o que, si escribe una parte de la dirección URL, no incluya caracteres ni espacios especiales. Deje este cuadro en blanco para devolver las entradas de todos los archivos y carpetas de la organización.

4. Haga clic en **Buscar** para ejecutar la búsqueda.

Se muestra una nueva página que muestra que se está ejecutando la búsqueda de registros de auditoría. Cuando se completa la búsqueda, los registros de auditoría se muestran en la página. Haga clic en un registro para mostrar una página de control flotante con propiedades detalladas.

Para obtener instrucciones más detalladas, consulte [Búsqueda en el registro de auditoría en el centro de cumplimiento](search-the-audit-log-in-security-and-compliance.md).
