---
title: Vaya al Centro de actividades para ver y aprobar las tareas de investigación y corrección automatizadas
description: Use el Centro de acciones para ver detalles sobre la investigación automatizada y aprobar acciones pendientes
keywords: Centro de acción, protección contra amenazas, investigación, alerta, pendiente, automatizada, detección
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
ms.date: 07/27/2022
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.openlocfilehash: b82d40a1bc12b480851de3ecaec639717b3c00c7
ms.sourcegitcommit: e8dd5cd434d17af7096d28d467a2b3b021cbb233
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "67051808"
---
# <a name="the-action-center"></a>El Centro de actividades

**Se aplica a:**
- Microsoft 365 Defender

El Centro de acciones proporciona una experiencia de "un solo panel de cristal" para las tareas de incidentes y alertas, como:

- Aprobación de acciones de corrección pendientes.
- Visualización de un registro de auditoría de acciones de corrección ya aprobadas.
- Revisión de las acciones de corrección completadas.

Dado que el Centro de acciones proporciona una visión completa de Microsoft 365 Defender en el trabajo, el equipo de operaciones de seguridad puede funcionar de forma más eficaz y eficaz.

## <a name="the-unified-action-center"></a>Centro de acciones unificado

El Centro de acciones unificado ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) muestra las acciones de corrección pendientes y completadas para los dispositivos, el correo electrónico & el contenido de colaboración y las identidades en una sola ubicación.

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Centro de acciones unificado en el portal de Microsoft 365 Defender." lightbox="../../media/m3d-action-center-unified.png":::

Por ejemplo: 

- Si anteriormente usaba el Centro de cumplimiento de Office 365 Security & ([https://protection.office.com](https://protection.office.com)), pruebe el Centro de acciones unificado en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>.
- Si usaba el Centro de acciones en el Centro de seguridad de Microsoft Defender ([https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)), pruebe el Centro de acciones unificado en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>.
- Si ya usaba el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>, verá varias mejoras en el Centro de acciones ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)).

El Centro de acciones unificado reúne acciones de corrección en Defender para punto de conexión y Defender para Office 365. Define un lenguaje común para todas las acciones de corrección y proporciona una experiencia de investigación unificada. El equipo de operaciones de seguridad tiene una experiencia de "un solo panel de cristal" para ver y administrar las acciones de corrección.  

Puede usar el Centro de acciones unificado si tiene los permisos adecuados y una o varias de las siguientes suscripciones:

- [Defender para punto de conexión](../defender-endpoint/microsoft-defender-endpoint.md)
- [Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)
- [Microsoft 365 Defender](microsoft-365-defender.md)

> [!TIP]
> Para obtener más información, consulte [Requisitos](./prerequisites.md).

Puede navegar a la lista de acciones pendientes de aprobación de dos maneras diferentes:

- Vaya a [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center); o
- En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en la tarjeta de respuesta Investigación automatizada &, seleccione **Aprobar en el Centro de acciones**.

## <a name="using-the-action-center"></a>Uso del Centro de acciones

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a> e inicie sesión. 

2. En el panel de navegación, elija **Centro de actividades**. O bien, en la tarjeta Investigación automatizada & respuesta, seleccione **Aprobar en el Centro de acciones**.

3. Use las **pestañas Acciones pendientes** e **Historial** . En la tabla siguiente se resume lo que verá en cada pestaña:

   |Pestaña  |Descripción  |
   |---------|---------|
   |**Pending**     | Muestra una lista de acciones que requieren atención. Puede aprobar o rechazar acciones de una en una, o seleccionar varias acciones si tienen el mismo tipo de acción (como el archivo de cuarentena). <br/><br/>Asegúrese de revisar y aprobar (o rechazar) las acciones pendientes lo antes posible para que las investigaciones automatizadas puedan completarse de forma oportuna.       |
   |**Historial**     | Actúa como registro de auditoría para las acciones que se realizaron, como: <br/>- Acciones de corrección que se realizaron como resultado de investigaciones automatizadas <br/>- Acciones de corrección que se realizaron en mensajes de correo electrónico sospechosos o malintencionados, archivos o direcciones URL<br/>- Acciones de corrección aprobadas por el equipo de operaciones de seguridad <br/>- Comandos que se ejecutaron y acciones de corrección que se aplicaron durante las sesiones de live response<br/>- Acciones de corrección realizadas por la protección antivirus<br/><br/>Proporciona una manera de deshacer ciertas acciones (consulte [Deshacer acciones completadas](m365d-autoir-actions.md#undo-completed-actions)).        |

4. Puede personalizar, ordenar, filtrar y exportar datos en el Centro de acciones.

   :::image type="content" source="../../media/m3d-action-center-columnsfilters.png" alt-text="Captura de pantalla que muestra las funcionalidades de ordenación, filtrado y personalización del Centro de acciones." lightbox="../../media/m3d-action-center-columnsfilters.png":::

   - Seleccione un encabezado de columna para ordenar los elementos en orden ascendente o descendente.
   - Use el filtro de período de tiempo para ver los datos del último día, semana, 30 días o 6 meses.
   - Elija las columnas que desea ver.
   - Especifique cuántos elementos se van a incluir en cada página de datos.
   - Use filtros para ver solo los elementos que desea ver.
   - Seleccione **Exportar** para exportar los resultados a un archivo .csv.

## <a name="actions-tracked-in-the-action-center"></a>Acciones de las que se realiza un seguimiento en el Centro de acciones

Todas las acciones de corrección, tanto si están pendientes de aprobación como si ya se han aprobado, se consolidan en el Centro de actividades. Entre las acciones disponibles se incluyen las siguientes:

- Recopilar el paquete de investigación 
- Aislar el dispositivo (esta acción se puede deshacer) 
- Retirar la máquina 
- Ejecutar el código de versión 
- Liberar de cuarentena 
- Solicitar ejemplo 
- Restringir la ejecución de código (esta acción se puede deshacer) 
- Ejecutar examen de antivirus 
- Detener y poner en cuarentena un archivo 
- Contener dispositivos de la red

Además de las acciones de corrección que se realizan automáticamente como resultado de [investigaciones automatizadas](m365d-autoir.md), el Centro de acciones también realiza un seguimiento de las acciones que el equipo de seguridad ha llevado a cabo para abordar las amenazas detectadas y las acciones que se realizaron como resultado de las características de protección contra amenazas en Microsoft 365 Defender. Para obtener más información sobre las acciones de corrección automáticas y manuales, consulte [Acciones de corrección](m365d-remediation-actions.md).

## <a name="viewing-action-source-details"></a>Visualización de los detalles del origen de la acción

(**¡NUEVO!**) El Centro de acciones mejorado ahora incluye una columna **De origen de acción** que le indica de dónde procede cada acción. En la tabla siguiente se describen los posibles valores **de origen de acción** :

| Valor de origen de acción | Descripción |
|:-----|:---|
| **Acción manual del dispositivo** | Una acción manual realizada en un dispositivo. Algunos ejemplos son el [aislamiento del dispositivo](../defender-endpoint/respond-machine-alerts.md#isolate-devices-from-the-network) o la [cuarentena de archivos](../defender-endpoint/respond-file-alerts.md#stop-and-quarantine-files). |
| **Acción de correo electrónico manual** | Una acción manual realizada en el correo electrónico. Un ejemplo incluye la eliminación temporal de mensajes de correo electrónico o [la corrección de un mensaje de correo electrónico](../office-365-security/remediate-malicious-email-delivered-office-365.md). |
| **Acción de dispositivo automatizada** | Una acción automatizada realizada en una entidad, como un archivo o un proceso. Entre los ejemplos de acciones automatizadas se incluyen el envío de un archivo a la cuarentena, la detención de un proceso y la eliminación de una clave del Registro. (Consulte [Acciones de corrección en Microsoft Defender para punto de conexión](../defender-endpoint/manage-auto-investigation.md#remediation-actions)). |
| **Acción de correo electrónico automatizada** | Una acción automatizada realizada en el contenido del correo electrónico, como un mensaje de correo electrónico, datos adjuntos o dirección URL. Entre los ejemplos de acciones automatizadas se incluyen la eliminación temporal de mensajes de correo electrónico, el bloqueo de direcciones URL y la desactivación del reenvío de correo externo. (Consulte [Acciones de corrección en Microsoft Defender para Office 365](../office-365-security/air-remediation-actions.md)). |
| **Acción de búsqueda avanzada** | Acciones realizadas en dispositivos o correo electrónico con [búsqueda avanzada](./advanced-hunting-overview.md). |
| **Acción del Explorador** | Acciones realizadas en el contenido del correo electrónico con [el Explorador](../office-365-security/threat-explorer.md). |
| **Acción de respuesta dinámica manual** | Acciones realizadas en un dispositivo con [respuesta dinámica](../defender-endpoint/live-response.md). Algunos ejemplos son la eliminación de un archivo, la detención de un proceso y la eliminación de una tarea programada. |
| **Acción de respuesta dinámica** | Acciones realizadas en un dispositivo con [api de Microsoft Defender para punto de conexión](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis). Algunos ejemplos de acciones son aislar un dispositivo, ejecutar un examen antivirus y obtener información sobre un archivo. |

## <a name="required-permissions-for-action-center-tasks"></a>Permisos necesarios para las tareas del Centro de actividades

Para realizar tareas, como aprobar o rechazar acciones pendientes en el Centro de acciones, debe tener permisos asignados como se muestra en la tabla siguiente:

|Acción de corrección |Permisos y roles necesarios |
|--|----|
|Microsoft Defender para punto de conexión corrección (dispositivos) |**Rol administrador de seguridad** asignado en Azure Active Directory (Azure AD) ([https://portal.azure.com](https://portal.azure.com)) o el Centro de administración de Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- o ---<br/>**Rol de acciones de corrección activo** asignado en Microsoft Defender para punto de conexión <br/> <br/> Para obtener más información, consulte los siguientes recursos: <br/>- [Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference)<br/>- [Creación y administración de roles para el control de acceso basado en rol (Microsoft Defender para punto de conexión)](../defender-endpoint/user-roles.md)  |
|Microsoft Defender para Office 365 corrección (contenido y correo electrónico de Office)  |**Rol administrador de seguridad** asignado en Azure AD ([https://portal.azure.com](https://portal.azure.com)) o en el Centro de administración de Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- y --- <br/>**Rol de búsqueda y purga** asignado en el Centro de cumplimiento de seguridad & ([https://protection.office.com](https://protection.office.com)) <br/><br/>**IMPORTANTE**: Si tiene asignado el rol **Administrador de seguridad** solo en Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), no podrá acceder al Centro de acciones ni a las funcionalidades de Microsoft 365 Defender. Debe tener asignado el rol **Administrador de seguridad** en Azure AD o el Centro de administración de Microsoft 365. <br/><br/>Para obtener más información, consulte los siguientes recursos: <br/>- [Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference)<br/>- [Permisos en el Centro de cumplimiento de & de seguridad](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!TIP]
> Los usuarios que tengan asignado el rol **de administrador global** en Azure AD pueden aprobar o rechazar cualquier acción pendiente en el Centro de acciones. Sin embargo, como procedimiento recomendado, la organización debe limitar el número de personas que tienen asignado el rol **de administrador global** . Se recomienda usar el **administrador de seguridad**, **las acciones de corrección activas** y los roles **de búsqueda y purga** enumerados en la tabla anterior para los permisos del Centro de acciones.

## <a name="next-step"></a>Paso siguiente 

- [Ver y aprobar acciones de corrección](m365d-autoir-actions.md)
