---
title: Vaya al Centro de actividades para ver y aprobar las tareas de investigación y corrección automatizadas
description: Use el Centro de actividades para ver los detalles de la investigación automatizada y aprobar las acciones pendientes.
keywords: Centro de actividades, protección contra amenazas, investigación, alerta, pendiente, automatizada, detección
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.technology: m365d
ms.openlocfilehash: 45e02e4ce7d5d813cc8215a1f27ed9c415707cb1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930431"
---
# <a name="the-action-center"></a>El centro de actividades

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Use el Centro de acciones ( ) para ver los resultados de las investigaciones actuales y pasadas en los dispositivos y buzones de [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) correo de su organización. Según el tipo de amenaza y el veredicto [resultante,](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) las acciones de corrección pueden producirse automáticamente o tras la aprobación por parte del equipo de operaciones de seguridad de la organización. Todas las acciones de corrección, tanto si están pendientes de aprobación como si ya se han aprobado, se consolidan en el Centro de actividades. 

![Centro de actividades](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>Una perspectiva centralizada

El Centro de actividades proporciona una perspectiva centralizada de diferentes tareas, como, por ejemplo:
- Aprobación de las acciones de corrección pendientes;
- Visualización de un registro de auditoría de las acciones de corrección ya aprobadas; y
- Revisión de las acciones de corrección completadas.

El equipo de operaciones de seguridad puede funcionar de forma más eficaz y eficaz, ya que el Centro de actividades proporciona una vista completa de Microsoft 365 Defender en el trabajo.

## <a name="go-to-the-action-center"></a>Vaya al Centro de actividades

1. Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión. 

2. En el panel de navegación, elija **Centro de actividades**. 

3. En el Centro de acciones, verá dos pestañas: **Pendiente** e **Historial.**

    - En la pestaña **Pendientes** se muestran las investigaciones que deben ser revisadas y aprobadas por un miembro del equipo de operaciones de seguridad para poder continuar. Asegúrese de revisar los elementos pendientes que vea aquí y tomar las medidas necesarias al respecto.

    - En la pestaña **Historial** se muestran las investigaciones pasadas y las acciones de corrección que se han ejecutado automáticamente. Puede ver los datos del día, la semana, el mes o los seis meses anteriores.

4. Para mostrar solo las columnas que quiera ver, seleccione **Personalizar columnas**.<br/>![Centro de acciones en Microsoft 365 Defender](../../media/mtp-action-center.png)

5. Seleccione un elemento de la lista para ver más detalles sobre una investigación. Se abrirá la vista de detalles de la investigación.<br/>![Detalles de la investigación](../../media/mtp-air-investdetails.png)

    - Si la investigación pertenece al contenido del correo electrónico (por ejemplo, la entidad es un buzón), los detalles de la investigación se abren en el Centro de seguridad & cumplimiento ( [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) ). 

    - Si la investigación está relacionada con un dispositivo, los detalles de la investigación se abren en el centro de seguridad ([https://security.microsoft.com](https://security.microsoft.com)). 

> [!TIP]
> Si cree que se ha perdido algo o que las características de investigación y respuesta automatizadas de Microsoft 365 Defender han detectado algo incorrectamente, háganoslo saber. Vea cómo informar de falsos positivos/negativos en las capacidades de investigación y respuesta [automatizada (AIR) en Microsoft 365 Defender.](mtp-autoir-report-false-positives-negatives.md)

## <a name="available-actions"></a>Acciones disponibles

A medida que se toman medidas correctivas, aparecen en la **pestaña** Historial del Centro de actividades. Entre estas acciones se incluyen las siguientes:

- Recopilar paquete de investigación 
- Aislar dispositivo (esta acción se puede deshacer) 
- Equipo de bajada 
- Ejecución de código de lanzamiento 
- Liberar de cuarentena 
- Ejemplo de solicitud 
- Restringir la ejecución de código (esta acción se puede deshacer) 
- Ejecutar examen antivirus 
- Detener y poner en cuarentena 

> [!NOTE]
> Además de las acciones de corrección que se llevan a cabo automáticamente, el equipo de operaciones de seguridad puede realizar acciones manuales para solucionar las amenazas detectadas. Para obtener más información acerca de las acciones de corrección automáticas y manuales, vea [Acciones de corrección.](mtp-remediation-actions.md)

## <a name="action-source"></a>Origen de la acción

(**¡NUEVO!**) Como sabe, Microsoft 365 Defender reúne capacidades automatizadas de investigación y respuesta en varios servicios, como [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para Endpoint y Microsoft Defender para [Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) El centro de acciones nuevo y mejorado ahora incluye una columna **de** origen de acción que indica de dónde viene cada acción de corrección. 

En la tabla siguiente se describen los posibles **valores de origen de** acción:

| Valor de origen de la acción | Descripción |
|:-----|:---|
| **Acción manual del dispositivo** | Una acción manual realizada en un dispositivo. Algunos ejemplos son [el aislamiento de dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network) o la [cuarentena de archivos.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#stop-and-quarantine-files) |
| **Acción de correo electrónico manual** | Una acción manual realizada en el correo electrónico. Un ejemplo incluye la eliminación de forma flexible de mensajes de correo electrónico o [la corrección de un mensaje de correo electrónico.](https://docs.microsoft.com/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365) |
| **Acción automatizada del dispositivo** | Una acción automatizada realizada en una entidad, como un archivo o proceso. Entre los ejemplos de acciones automatizadas se incluyen el envío de un archivo a cuarentena, la detención de un proceso y la eliminación de una clave del Registro. (Vea [acciones de corrección en Microsoft Defender para endpoint).](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-auto-investigation#remediation-actions) |
| **Acción de correo electrónico automatizada** | Una acción automatizada realizada en el contenido del correo electrónico, como un mensaje de correo electrónico, datos adjuntos o dirección URL. Entre los ejemplos de acciones automatizadas se incluyen la eliminación de forma flexible de mensajes de correo electrónico, el bloqueo de direcciones URL y la desactivación del reenvío de correo externo. (Vea [acciones de corrección en Microsoft Defender para Office 365).](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions) |
| **Acción de búsqueda avanzada** | Acciones realizadas en dispositivos o correo electrónico con [búsqueda avanzada.](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview) |
| **Acción del explorador** | Acciones realizadas en el contenido de correo electrónico con [el Explorador.](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) |
| **Acción de respuesta en directo manual** | Acciones realizadas en un dispositivo con [respuesta en directo.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) Algunos ejemplos son la eliminación de un archivo, la detención de un proceso y la eliminación de una tarea programada. |
| **Acción de respuesta en directo** | Acciones realizadas en un dispositivo con [Microsoft Defender para las API de punto de conexión.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis) Entre los ejemplos de acciones se incluyen el aislamiento de un dispositivo, la ejecución de un examen antivirus y la obtención de información sobre un archivo. |

## <a name="required-permissions-for-action-center-tasks"></a>Permisos necesarios para las tareas del Centro de actividades

Para aprobar o rechazar las acciones pendientes en el Centro de actividades, debe tener asignados los permisos que se indican en la tabla siguiente:

|Acción de corrección |Permisos y roles necesarios |
|--|----|
|Corrección de Microsoft Defender para puntos de conexión (dispositivos) |Rol de administrador de seguridad asignado en Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) o en el Centro de administración de Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- o ---<br/>Rol acciones de corrección activas asignadas en Microsoft Defender para Endpoint <br/> <br/> Para obtener más información, vea los siguientes recursos: <br/>- [Permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Crear y administrar roles para el control de acceso basado en roles (Microsoft Defender para endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Corrección de Microsoft Defender para Office 365 (contenido y correo electrónico de Office)  |Rol de administrador de seguridad asignado en Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) o en el Centro de administración de Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- y --- <br/>Rol Buscar y purgar asignado al Centro de seguridad & cumplimiento ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**IMPORTANTE:** Si tiene asignado el rol administrador de seguridad solo en el Centro de seguridad & Cumplimiento, no podrá acceder al Centro de acciones ni a las capacidades de Microsoft 365 Defender. Debe tener el rol de administrador de seguridad asignado en Azure Active Directory o en el Centro de administración de Microsoft 365. <br/><br/>Para obtener más información, vea los siguientes recursos: <br/>- [Permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Permisos en el Centro de seguridad & cumplimiento](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Los usuarios que tienen el rol de administrador global asignado en Azure Active Directory pueden aprobar o denegar cualquier acción pendiente en el Centro de actividades. No obstante, el procedimiento recomendado es que la organización limite el número de usuarios que tienen asignado el rol de administrador global. Le recomendamos que use los roles de administrador de seguridad, acciones de corrección activas y búsqueda y purga enumerados anteriormente para los permisos del Centro de actividades.

## <a name="next-steps"></a>Siguientes pasos 

- [Aprobar o rechazar acciones pendientes después de una investigación automatizada](mtp-autoir-actions.md)
- [Ver los resultados de una investigación automatizada](mtp-autoir-results.md)

