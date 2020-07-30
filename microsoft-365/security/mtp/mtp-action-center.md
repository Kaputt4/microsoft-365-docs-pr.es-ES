---
title: Vaya al Centro de actividades para ver y aprobar las tareas de investigación y corrección automatizadas
description: Use el Centro de actividades para ver los detalles de la investigación automatizada y aprobar las acciones pendientes.
keywords: Centro de actividades, protección contra amenazas, investigación, alerta, pendiente, automatizada, detección
search.appverid: met150
ms.prod: M365-security-compliance
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 77bc0f088a9779396a56a9cc8cc9ae6ecbdadea7
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503108"
---
# <a name="the-action-center"></a>El centro de actividades

**Se aplica a:**
- Protección contra amenazas de Microsoft

Use el centro de actividades para ver los resultados de las investigaciones actuales y pasadas en los buzones y dispositivos de su organización. Según el tipo de amenaza y el veredicto resultante, [las acciones de corrección](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) se producen automáticamente o al aprobarlas por parte del equipo de operaciones de seguridad de la organización. Todas las acciones de corrección, tanto si están pendientes de aprobación como si ya se han aprobado, se consolidan en el Centro de actividades. 

![Centro de actividades](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>Una perspectiva centralizada

El Centro de actividades proporciona una perspectiva centralizada de diferentes tareas, como, por ejemplo:
- Aprobación de las acciones de corrección pendientes;
- Visualización de un registro de auditoría de las acciones de corrección ya aprobadas; y
- Revisión de las acciones de corrección completadas.

El equipo de operaciones de seguridad puede trabajar con más eficacia y eficiencia, ya que el Centro de actividades ofrece una vista integral de la Protección contra amenazas de Microsoft en el trabajo.

## <a name="go-to-the-action-center"></a>Vaya al Centro de actividades

1. Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión. 

2. En el panel de navegación, elija **Centro de actividades**. 

3. En el centro de actividades, verá dos pestañas: **pendiente** e **historial**.

    - En la pestaña **Pendientes** se muestran las investigaciones que deben ser revisadas y aprobadas por un miembro del equipo de operaciones de seguridad para poder continuar. Asegúrese de revisar los elementos pendientes que vea aquí y tomar las medidas necesarias al respecto.

    - En la pestaña **Historial** se muestran las investigaciones pasadas y las acciones de corrección que se han ejecutado automáticamente. Puede ver los datos del día, la semana, el mes o los seis meses anteriores.

4. Para mostrar solo las columnas que quiera ver, seleccione **Personalizar columnas**.<br/>![Centro de actividades en la Protección contra amenazas de Microsoft](../../media/mtp-action-center.png)

5. Seleccione un elemento de la lista para ver más detalles sobre una investigación. Se abrirá la vista de detalles de la investigación.<br/>![Detalles de la investigación](../../media/mtp-air-investdetails.png)

    - Si la investigación se aplica al contenido de correo electrónico (como, por ejemplo, la entidad es un buzón de correo), los detalles de investigación se abren en el centro de seguridad & cumplimiento ( [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) ). 

    - Si la investigación está relacionada con un dispositivo, los detalles de la investigación se abren en el centro de seguridad ([https://security.microsoft.com](https://security.microsoft.com)). 

> [!TIP]
> Si cree que algo ha perdido o detectado erróneamente las características de respuesta e investigación automatizada en la protección contra amenazas de Microsoft, háganoslo saber. Consulte [Cómo informar de falsos positivos/negativos en capacidades de investigación y respuesta automatizadas (Air) en la protección contra amenazas de Microsoft](mtp-autoir-report-false-positives-negatives.md).

## <a name="available-actions"></a>Acciones disponibles

A medida que se realizan acciones de corrección, aparecen en la pestaña historial del centro de actividades. Estas acciones incluyen las siguientes:

- Recopilar paquete de investigación 
- Aislar dispositivo (se puede deshacer esta acción) 
- Máquina desincorpora 
- Liberar la ejecución de código 
- Liberar de cuarentena 
- Ejemplo de solicitud 
- Restringir la ejecución de código (esta acción se puede deshacer) 
- Ejecutar detección de virus 
- Detener y poner en cuarentena 

## <a name="required-permissions-for-action-center-tasks"></a>Permisos necesarios para las tareas del Centro de actividades

Para aprobar o rechazar las acciones pendientes en el Centro de actividades, debe tener asignados los permisos que se indican en la tabla siguiente:

|Acción de corrección |Permisos y roles necesarios |
|--|----|
|Corrección de ATP de Microsoft Defender (dispositivos) |Rol de administrador de seguridad asignado en Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) o en el Centro de administración de Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- o ---<br/>Rol de acciones de corrección activas asignado en ATP de Microsoft Defender. <br/> <br/> Para obtener más información, vea los siguientes recursos: <br/>- [Permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Crear y administrar roles para el control de acceso basado en roles (ATP de Microsoft Defender)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Corrección de ATP de Office 365 (contenido de Office y correo electrónico)  |Rol de administrador de seguridad asignado en Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) o en el Centro de administración de Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- y --- <br/>Rol de búsqueda y depuración asignado al centro de seguridad & cumplimiento ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**Importante**: Si tiene asignado el rol de administrador de seguridad en el centro de seguridad & cumplimiento, no podrá acceder al centro de actividades ni a las capacidades de Microsoft Threat Protection. Debe tener el rol de administrador de seguridad asignado en Azure Active Directory o en el Centro de administración de Microsoft 365. <br/><br/>Para obtener más información, vea los siguientes recursos: <br/>- [Permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Permisos en el centro de seguridad & cumplimiento](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Los usuarios que tienen el rol de administrador global asignado en Azure Active Directory pueden aprobar o denegar cualquier acción pendiente en el Centro de actividades. No obstante, el procedimiento recomendado es que la organización limite el número de usuarios que tienen asignado el rol de administrador global. Le recomendamos que use los roles de administrador de seguridad, acciones de corrección activas y búsqueda y purga enumerados anteriormente para los permisos del Centro de actividades.

## <a name="next-steps"></a>Siguientes pasos 

- [Obtenga más información sobre los incidentes en la Protección contra amenazas de Microsoft](incidents-overview.md)

- [Ver los resultados de una investigación automatizada](mtp-autoir-results.md)

- [Obtenga más información sobre la búsqueda avanzada en la Protección contra amenazas de Microsoft](advanced-hunting-overview.md)

