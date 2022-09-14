---
title: Revisar las acciones de corrección después de las investigaciones automatizadas
description: Revise y apruebe (o rechace) las acciones de corrección después de una investigación automatizada.
keywords: autoir, automatizado, investigación, detección, corrección, acción, pendiente, aprobado
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
ms.localizationpriority: medium
ms.date: 07/20/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.custom: admindeeplinkDEFENDER
ms.topic: how-to
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 4bad45f7ed9e6c5e82f1bbc52603deeb6c104af1
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67689905"
---
# <a name="review-remediation-actions-following-an-automated-investigation"></a>Revisar las acciones de corrección después de una investigación automatizada

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para Empresas](../defender-business/mdb-overview.md)

## <a name="remediation-actions"></a>Acciones de corrección

Cuando se ejecuta una [investigación automatizada](automated-investigations.md) , se genera un veredicto para cada pieza de evidencia investigada. Los veredictos pueden ser *Malintencionados*, *Sospechosos* o *No se encuentran amenazas*.

Dependiendo

- el tipo de amenaza,
- el veredicto resultante, y
- cómo se configuran los [grupos de dispositivos](/microsoft-365/security/defender-endpoint/machine-groups) de la organización,

las acciones de corrección pueden producirse automáticamente o solo tras la aprobación por parte del equipo de operaciones de seguridad de la organización.

Estos son algunos ejemplos:

- **Ejemplo 1**: Los grupos de dispositivos de Fabrikam se establecen en **Completo: corregir amenazas automáticamente** (la configuración recomendada). En este caso, las acciones de corrección se realizan automáticamente para los artefactos que se consideran malintencionados después de una investigación automatizada (consulte [Revisar las acciones completadas](#review-completed-actions)).

- **Ejemplo 2**: Los dispositivos de Contoso se incluyen en un grupo de dispositivos establecido para **Semi: requieren aprobación para cualquier corrección**. En este caso, el equipo de operaciones de seguridad de Contoso debe revisar y aprobar todas las acciones de corrección después de una investigación automatizada (consulte [Revisión de las acciones pendientes](#review-pending-actions)).

- **Ejemplo 3**: Tailspin Toys tiene sus grupos de dispositivos establecidos en **Sin respuesta automatizada** (no recomendado). En este caso, no se producen investigaciones automatizadas. No se realizan acciones de corrección o están pendientes, y no se registran acciones en el [Centro](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center) de acciones para sus dispositivos (consulte [Administración de grupos de dispositivos](/microsoft-365/security/defender-endpoint/machine-groups#manage-device-groups)).

Ya sea que se realice automáticamente o tras la aprobación, una investigación automatizada puede dar lugar a una o varias de las acciones de corrección:

- Poner en cuarentena un archivo
- Eliminación de una clave del Registro
- Eliminación de un proceso
- Detener un servicio
- Deshabilitar un controlador
- Eliminación de una tarea programada

## <a name="review-pending-actions"></a>Revisión de las acciones pendientes

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a> e inicie sesión.

2. En el panel de navegación, elija **Centro de actividades**.

3. Revise los elementos de la pestaña **Pendiente** .

4. Seleccione una acción para abrir su panel flotante.

5. En el panel flotante, revise la información y, a continuación, realice uno de los pasos siguientes:

   - Seleccione **Abrir página de investigación** para ver más detalles sobre la investigación.
   - Seleccione **Aprobar** para iniciar una acción pendiente.
   - Seleccione **Rechazar** para evitar que se realice una acción pendiente.
   - Seleccione **Ir a buscar** para ir a [Búsqueda avanzada](advanced-hunting-overview.md).

## <a name="review-completed-actions"></a>Revisar las acciones completadas

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a> e inicie sesión.

2. En el panel de navegación, elija **Centro de actividades**.

3. Revise los elementos de la pestaña **Historial** .

4. Seleccione un elemento para ver más detalles sobre esa acción de corrección.

## <a name="undo-completed-actions"></a>Deshacer acciones completadas

Si ha determinado que un dispositivo o un archivo no es una amenaza, puede deshacer las acciones de corrección que se realizaron, independientemente de si esas acciones se realizaron de forma automática o manual. En el Centro de acciones, en la pestaña **Historial** , puede deshacer cualquiera de las siguientes acciones:

|Origen de la acción|Acciones admitidas|
|---|---|
|<ul><li>Investigación automatizada</li><li>Acciones de respuesta manual (consulte la nota siguiente)</li><li>Antivirus de Microsoft Defender</li></ul>|<ul><li>Deshabilitar un controlador</li><li>Aislar el dispositivo</li><li>Poner en cuarentena un archivo</li><li>Eliminación de una clave del Registro</li><li>Eliminación de una tarea programada</li><li>Restringir la ejecución del código</li><li>Detener un servicio</li></ul>|

> [!NOTE]
> El plan 1 y [Microsoft Defender para Empresas](../defender-business/mdb-overview.md) de [Defender para punto de conexión](defender-endpoint-plan-1.md) incluyen solo las siguientes acciones de respuesta manual:
>
> - Ejecutar examen de antivirus
> - Aislar el dispositivo
> - Detener y poner en cuarentena un archivo
> - Adición de un indicador para bloquear o permitir un archivo
>
> Para más información, consulte [Comparación de planes Microsoft Defender para punto de conexión](defender-endpoint-plan-1-2.md) y [Comparación de características de seguridad en planes de Microsoft 365 para pequeñas y medianas empresas](../defender-business/compare-mdb-m365-plans.md).

### <a name="to-undo-multiple-actions-at-one-time"></a>Para deshacer varias acciones a la vez

1. Vaya al Centro de acciones ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) e inicie sesión.

2. En la pestaña **Historial** , seleccione las acciones que desea deshacer. Asegúrese de seleccionar elementos que tengan el mismo tipo de acción. Se abre un panel flotante.

3. En el panel flotante, seleccione **Deshacer**.

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Para quitar un archivo de la cuarentena en varios dispositivos

1. Vaya al Centro de acciones ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) e inicie sesión.

2. En la pestaña **Historial** , seleccione un elemento que tenga el **archivo de cuarentena** Tipo de acción.

3. En el panel flotante, seleccione **Aplicar a X más instancias de este archivo** y, a continuación, seleccione **Deshacer**.

## <a name="automation-levels-automated-investigation-results-and-resulting-actions"></a>Niveles de automatización, resultados de investigación automatizados y acciones resultantes

Los niveles de automatización afectan a si ciertas acciones de corrección se realizan automáticamente o solo tras la aprobación. A veces, el equipo de operaciones de seguridad tiene más pasos que seguir, en función de los resultados de una investigación automatizada. En la tabla siguiente se resumen los niveles de automatización, los resultados de las investigaciones automatizadas y qué hacer en cada caso.

|Configuración del grupo de dispositivos|Resultados de la investigación automatizada|Qué hacer|
|---|---|---|
|**Completo: corrección automática de amenazas**<br/>(recomendado)|Se llega a un veredicto de *Malintencionada* para una prueba. <p> Las acciones de corrección adecuadas se realizan automáticamente.|[Revisar las acciones completadas](#review-completed-actions) |
|**Semi: requiere aprobación para cualquier corrección.**|Se llega a un veredicto de *malintencionada* o *sospechosa* para una prueba. <p> Las acciones de corrección están pendientes de aprobación para continuar.|[Aprobar (o rechazar) acciones pendientes](#review-pending-actions)|
|**Semi: se requiere aprobación para la corrección de carpetas principales**|Se llega a un veredicto de *Malintencionada* para una prueba. <p> Si el artefacto es un archivo o ejecutable y se encuentra en un directorio del sistema operativo, como la carpeta Windows o la carpeta Archivos de programa, las acciones de corrección están pendientes de aprobación. <p> Si el artefacto *no* está en un directorio del sistema operativo, las acciones de corrección se realizan automáticamente.|<ol><li>[Aprobar (o rechazar) acciones pendientes](#review-pending-actions)</li><li>[Revisar las acciones completadas](#review-completed-actions)</li></ol>|
|**Semi: se requiere aprobación para la corrección de carpetas principales**|Se llega a un veredicto de *sospechoso* para una prueba. <p> Las acciones de corrección están pendientes de aprobación.|[Aprobar (o rechazar) las acciones pendientes](#review-pending-actions).|
|**Semi: se requiere aprobación para la corrección de carpetas no temporales**|Se llega a un veredicto de *Malintencionada* para una prueba. <p> Si el artefacto es un archivo o ejecutable que no está en una carpeta temporal, como la carpeta de descargas del usuario o la carpeta temporal, las acciones de corrección están pendientes de aprobación. <p> Si el artefacto es un archivo o ejecutable que *se encuentra* en una carpeta temporal, las acciones de corrección se realizan automáticamente.|<ol><li>[Aprobar (o rechazar) acciones pendientes](#review-pending-actions)</li><li>[Revisar las acciones completadas](#review-completed-actions)</li></ol>|
|**Semi: se requiere aprobación para la corrección de carpetas no temporales**|Se llega a un veredicto de *sospechoso* para una prueba. <p> Las acciones de corrección están pendientes de aprobación.|[Aprobar (o rechazar) acciones pendientes](#review-pending-actions)|
|Cualquiera de los niveles de automatización **completa** o **semiautomatización**|Se llega a un veredicto de *No se encontraron amenazas* para una prueba. <p> No se realizan acciones de corrección y no hay ninguna acción pendiente de aprobación.|[Ver detalles y resultados de las investigaciones automatizadas](/microsoft-365/security/defender-endpoint/auto-investigation-action-center)|
|**Ninguna respuesta automatizada** (no recomendada)|No se ejecutan investigaciones automatizadas, por lo que no se alcanza ningún veredicto y no se toman medidas correctivas ni se espera la aprobación.|[Considere la posibilidad de configurar o cambiar los grupos de dispositivos para usar la automatización **completa** o **semiautomatización**](/microsoft-365/security/defender-endpoint/machine-groups)|

Se realiza un seguimiento de todos los veredictos en el [Centro de acción](auto-investigation-action-center.md#the-unified-action-center).

> [!NOTE]
> En [Defender para empresas](../defender-business/mdb-overview.md), las funcionalidades automatizadas de investigación y corrección están preestablecidas para usar **Full : corregir amenazas automáticamente**. Estas funcionalidades se aplican a todos los dispositivos de forma predeterminada.

## <a name="next-steps"></a>Pasos siguientes

- [Más información sobre las funcionalidades de respuesta en vivo](live-response.md)
- [Búsqueda proactiva de amenazas con búsqueda avanzada](advanced-hunting-overview.md)
- [Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión](defender-endpoint-false-positives-negatives.md)

## <a name="see-also"></a>Vea también

- [Introducción a las investigaciones automatizadas](automated-investigations.md)
