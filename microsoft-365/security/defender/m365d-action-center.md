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
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: 7bea9a1632e7a9ed9d394c2c411123d0601a9397
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274585"
---
# <a name="the-action-center"></a>El centro de actividades

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

El Centro de acciones proporciona una experiencia de "panel único de cristal" para las tareas de incidentes y alertas, como:

- Aprobar acciones de corrección pendientes.
- Visualización de un registro de auditoría de acciones de corrección ya aprobadas.
- Revisión de las acciones de corrección completadas.

Dado que el Centro de acciones proporciona una vista completa de Microsoft 365 Defender en el trabajo, el equipo de operaciones de seguridad puede funcionar de forma más eficaz y eficiente.

## <a name="the-unified-action-center"></a>Centro de acciones unificado

El Centro de acciones unificado ( ) enumera las acciones de corrección pendientes y completadas para los dispositivos, el correo electrónico & de colaboración y las identidades [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) en una ubicación.

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Centro de acción unificado en Microsoft 365 Defender":::

Por ejemplo: 

- Si anteriormente estaba usando el Centro de seguridad y & cumplimiento de Office 365 ( ), pruebe el Centro de acciones unificado en el Centro de seguridad de [https://protection.office.com](https://protection.office.com) Microsoft 365 ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).
- Si estaba usando el Centro de acciones en el Centro de seguridad de Microsoft Defender ( ), pruebe el Centro de acción unificado en el Centro de seguridad de [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) Microsoft 365 ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).
- Si ya estaba usando el Centro de seguridad de Microsoft 365 ( ), verá varias mejoras en el [https://security.microsoft.com](https://security.microsoft.com) Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).

El Centro de acción unificado reúne acciones de corrección en Defender para Endpoint y Defender para Office 365. Define un lenguaje común para todas las acciones de corrección y proporciona una experiencia de investigación unificada. El equipo de operaciones de seguridad tiene una experiencia de "panel único de cristal" para ver y administrar acciones de corrección.  

Puede usar el Centro de acciones unificado si tiene los permisos adecuados y una o varias de las siguientes suscripciones:

- [Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)
- [Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)
- [Microsoft 365 Defender](microsoft-365-defender.md)

> [!TIP]
> Para obtener más información, vea [Requisitos](./prerequisites.md).

## <a name="using-the-action-center"></a>Uso del Centro de acciones

1. Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión. 
2. En el panel de navegación, elija **Centro de actividades**. 

Al visitar el Centro de acciones, verá dos pestañas: **Acciones pendientes** e **Historial**. En la tabla siguiente se resume lo que verá en cada pestaña:

|Pestaña  |Descripción  |
|---------|---------|
|**Pending**     | Muestra una lista de acciones que requieren atención. Puede aprobar o rechazar acciones de una en una, o seleccionar varias acciones si tienen el mismo tipo de acción (como el archivo de cuarentena). <p>**SUGERENCIA:** Asegúrese de revisar y aprobar (o rechazar) las acciones pendientes tan pronto como sea posible para que las investigaciones automatizadas puedan completarse de forma oportuna.       |
|**Historial**     | Sirve como registro de auditoría para las acciones que se han realizado, como: <br/>- Acciones de corrección que se realizaron como resultado de investigaciones automatizadas <br/>- Acciones de corrección realizadas en mensajes de correo electrónico, archivos o direcciones URL sospechosas o malintencionadas<br/>- Acciones de corrección aprobadas por el equipo de operaciones de seguridad <br/>- Comandos que se ejecutaron y acciones de corrección que se aplicaron durante las sesiones de Live Response<br/>- Acciones de corrección realizadas por la protección antivirus <p>Proporciona una forma de deshacer determinadas acciones (vea [Deshacer acciones completadas](m365d-autoir-actions.md#undo-completed-actions)).        |

Puede personalizar, ordenar, filtrar y exportar datos en el Centro de acciones.

:::image type="content" source="../../media/m3d-action-center-columnsfilters.png" alt-text="El Centro de acciones permite ordenar, filtrar y personalizar la lista de acciones":::

- Seleccione un encabezado de columna para ordenar los elementos en orden ascendente o descendente.
- Use el filtro de período de tiempo para ver los datos del último día, semana, 30 días o 6 meses.
- Elija las columnas que desea ver.
- Especifique cuántos elementos se deben incluir en cada página de datos.
- Use filtros para ver solo los elementos que desea ver.
- Seleccione **Exportar** para exportar resultados a un .csv archivo.

## <a name="actions-tracked-in-the-action-center"></a>Acciones realizadas en el Centro de acciones

Todas las acciones, tanto si están pendientes de aprobación como si ya se han realizado, se realiza un seguimiento en el Centro de acciones. Entre las acciones disponibles se incluyen las siguientes:

- Recopilar paquete de investigación 
- Aislar dispositivo (esta acción se puede deshacer) 
- Retirar máquina 
- Ejecución de código de versión 
- Liberar de la cuarentena 
- Ejemplo de solicitud 
- Restringir la ejecución de código (esta acción se puede deshacer) 
- Ejecutar examen antivirus 
- Detener y poner en cuarentena 

Además de las acciones de corrección que se toman automáticamente como resultado de investigaciones [automatizadas,](m365d-autoir.md)el Centro de acción también realiza un seguimiento de las acciones que el equipo de seguridad ha realizado para abordar las amenazas detectadas y las acciones que se han realizado como resultado de las características de protección contra amenazas en Microsoft 365 Defender. Para obtener más información acerca de las acciones de corrección automáticas y manuales, vea [Acciones de corrección](m365d-remediation-actions.md).

## <a name="viewing-action-source-details"></a>Visualización de detalles del origen de la acción

(**¡NUEVO!**) El Centro de acciones mejorado ahora incluye una **columna de origen** de acción que indica de dónde provenía cada acción. En la tabla siguiente se describen los **posibles valores de origen action:**

| Valor de origen de la acción | Descripción |
|:-----|:---|
| **Acción manual del dispositivo** | Una acción manual realizada en un dispositivo. Algunos ejemplos son [el aislamiento de dispositivos](../defender-endpoint/respond-machine-alerts.md#isolate-devices-from-the-network) o [la cuarentena de archivos.](../defender-endpoint/respond-file-alerts.md#stop-and-quarantine-files) |
| **Acción de correo electrónico manual** | Una acción manual realizada en el correo electrónico. Un ejemplo incluye la eliminación de mensajes de correo electrónico o [la corrección de un mensaje de correo electrónico](../office-365-security/remediate-malicious-email-delivered-office-365.md). |
| **Acción del dispositivo automatizado** | Una acción automatizada realizada en una entidad, como un archivo o un proceso. Entre los ejemplos de acciones automatizadas se incluyen el envío de un archivo a la cuarentena, la detención de un proceso y la eliminación de una clave del Registro. (Vea [Acciones de corrección en Microsoft Defender para Endpoint](../defender-endpoint/manage-auto-investigation.md#remediation-actions)).) |
| **Acción de correo electrónico automatizado** | Una acción automatizada realizada en el contenido del correo electrónico, como un mensaje de correo electrónico, datos adjuntos o una dirección URL. Entre los ejemplos de acciones automatizadas se incluyen la eliminación de mensajes de correo electrónico, el bloqueo de direcciones URL y la desactivación del reenvío de correo externo. (Vea [Acciones de corrección en Microsoft Defender para Office 365](../office-365-security/air-remediation-actions.md).) |
| **Acción de búsqueda avanzada** | Acciones realizadas en dispositivos o correo electrónico con [búsqueda avanzada.](./advanced-hunting-overview.md) |
| **Acción Explorador** | Acciones realizadas en el contenido de correo electrónico con [el Explorador](../office-365-security/threat-explorer.md). |
| **Acción de respuesta en directo manual** | Acciones realizadas en un dispositivo con [respuesta en directo](../defender-endpoint/live-response.md). Algunos ejemplos son la eliminación de un archivo, la detención de un proceso y la eliminación de una tarea programada. |
| **Acción de respuesta en directo** | Acciones realizadas en un dispositivo con [Microsoft Defender para api de punto de conexión](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis). Algunos ejemplos de acciones son aislar un dispositivo, ejecutar un examen antivirus y obtener información sobre un archivo. |

## <a name="required-permissions-for-action-center-tasks"></a>Permisos necesarios para las tareas del Centro de actividades

Para realizar tareas, como aprobar o rechazar acciones pendientes en el Centro de acciones, debe tener permisos asignados como se muestra en la tabla siguiente:

|Acción de corrección |Permisos y roles necesarios |
|--|----|
|Microsoft Defender para la corrección de puntos de conexión (dispositivos) |**Rol de administrador** de seguridad asignado en Azure Active Directory (Azure AD) ( ) o en el Centro de administración de [https://portal.azure.com](https://portal.azure.com) Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>--- o ---<br/>**Rol acciones de corrección activas** asignadas en Microsoft Defender para endpoint <br/> <br/> Para obtener más información, consulte los siguientes recursos: <br/>- [Permisos de roles de administrador en Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Crear y administrar roles para el control de acceso basado en roles (Microsoft Defender para endpoint)](../defender-endpoint/user-roles.md)  |
|Corrección de Microsoft Defender para Office 365 (contenido y correo electrónico de Office)  |**Rol de administrador** de seguridad asignado en Azure AD ( ) o en el Centro de administración [https://portal.azure.com](https://portal.azure.com) de Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>--- y --- <br/>**Función De búsqueda y** purga asignada en el Centro de seguridad & cumplimiento ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**IMPORTANTE:** Si tiene  asignado el rol Administrador de seguridad solo en el Centro de cumplimiento de Office 365 Security & ( ), no podrá acceder a las capacidades del Centro de acciones o [https://protection.office.com](https://protection.office.com) Microsoft 365 Defender. Debe tener asignado el rol **administrador de** seguridad en Azure AD o en el Centro de administración de Microsoft 365. <br/><br/>Para obtener más información, consulte los siguientes recursos: <br/>- [Permisos de roles de administrador en Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Permisos en el Centro de seguridad & cumplimiento](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!TIP]
> Los usuarios que tengan asignada la función **Administrador global** en Azure AD pueden aprobar o rechazar cualquier acción pendiente en el Centro de acciones. Sin embargo, como práctica recomendada, la organización debe limitar el número de personas que tienen asignado el rol **de administrador** global. Se recomienda usar los roles Administrador de  **seguridad,** **Acciones** de corrección activas y Roles de búsqueda y purga enumerados en la tabla anterior para permisos del Centro de acciones.

## <a name="next-step"></a>Paso siguiente 

- [Ver y administrar acciones de corrección](m365d-autoir-actions.md)
