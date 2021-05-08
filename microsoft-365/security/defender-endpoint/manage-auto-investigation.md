---
title: Revisar acciones de corrección tras investigaciones automatizadas
description: Revisar y aprobar (o rechazar) acciones de corrección después de una investigación automatizada.
keywords: autoir, automatizado, investigación, detección, corrección, acción, pendiente, aprobado
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.date: 01/29/2021
ms.technology: mde
ms.openlocfilehash: b0c983f4ba939cee6485570af774c8a728c73944
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274933"
---
# <a name="review-remediation-actions-following-an-automated-investigation"></a>Revisar acciones de corrección tras una investigación automatizada

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


## <a name="remediation-actions"></a>Acciones de corrección

Cuando se [ejecuta una investigación automatizada,](automated-investigations.md) se genera un veredicto para cada pieza de evidencia investigada. Los veredictos pueden ser *malintencionados,* sospechosos o *no se encuentran amenazas.*  

Dependiendo de

- el tipo de amenaza, 
- el veredicto resultante y 
- cómo se configuran los grupos [de dispositivos](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) de la organización, 

las acciones de corrección pueden producirse automáticamente o solo tras la aprobación del equipo de operaciones de seguridad de la organización. 

Estos son algunos ejemplos:

- **Ejemplo 1:** los grupos de dispositivos de Fabrikam se establecen en **Completo: corregir** las amenazas automáticamente (la configuración recomendada). En este caso, las acciones de corrección se toman automáticamente para artefactos que se consideran malintencionados después de una investigación automatizada (vea [Revisar acciones completadas](#review-completed-actions)).

- **Ejemplo 2:** Los dispositivos de Contoso se incluyen en un grupo de dispositivos establecido para Semi: requerir la aprobación **de cualquier corrección**. En este caso, el equipo de operaciones de seguridad de Contoso debe revisar y aprobar todas las acciones de corrección después de una investigación automatizada (vea [Revisar acciones pendientes](#review-pending-actions)).

- **Ejemplo 3:** Tailspin Toys tiene sus grupos de dispositivos establecidos en **No automated response** (no recomendado). En este caso, no se producen investigaciones automatizadas. No se han realizado acciones de corrección ni [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center) están pendientes y no se registra ninguna acción en el Centro de acciones para sus dispositivos (consulta [Administrar grupos de dispositivos).](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups#manage-device-groups)

Independientemente de si se realiza automáticamente o tras la aprobación, una investigación automatizada puede dar como resultado una o varias de las acciones de corrección:
- Poner en cuarentena un archivo
- Quitar una clave del Registro 
- Eliminación de un proceso 
- Detener un servicio 
- Deshabilitar un controlador 
- Quitar una tarea programada

## <a name="review-pending-actions"></a>Revisar acciones pendientes

1. Vaya al centro Microsoft 365 seguridad ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.
2. En el panel de navegación, elija **Centro de actividades**. 
3. Revise los elementos de la **pestaña** Pendiente. 
4. Seleccione una acción para abrir su panel desplegable.
5. En el panel desplegable, revise la información y, a continuación, siga uno de los pasos siguientes:
   - Seleccione **Abrir página de investigación** para ver más detalles sobre la investigación.
   - Seleccione **Aprobar** para iniciar una acción pendiente.
   - Seleccione **Rechazar** para evitar que se haga una acción pendiente.
   - Seleccione **Ir a la búsqueda** para ir a Búsqueda [avanzada.](advanced-hunting-overview.md) 

## <a name="review-completed-actions"></a>Revisar acciones completadas

1. Vaya al centro Microsoft 365 seguridad ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.
2. En el panel de navegación, elija **Centro de actividades**. 
3. Revise los elementos de la **pestaña** Historial. 
4. Seleccione un elemento para ver más detalles sobre esa acción de corrección.
 
## <a name="undo-completed-actions"></a>Deshacer acciones completadas

Si has determinado que un dispositivo o un archivo no es una amenaza, puedes deshacer las acciones de corrección que se realizaron, independientemente de si dichas acciones se realizaron de forma automática o manual. En el Centro de acciones, en la **ficha** Historial, puede deshacer cualquiera de las siguientes acciones:  

| Origen de la acción | Acciones admitidas |
|:---|:---|
| - Investigación automatizada <br/>- Antivirus de Microsoft Defender <br/>- Acciones de respuesta manuales | - Aislar dispositivo <br/>- Restringir la ejecución de código <br/>- Poner en cuarentena un archivo <br/>- Quitar una clave del Registro <br/>- Detener un servicio <br/>- Deshabilitar un controlador <br/>- Quitar una tarea programada |

### <a name="to-undo-multiple-actions-at-one-time"></a>Para deshacer varias acciones a la vez

1. Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e inicie sesión.
2. En la **pestaña** Historial, seleccione las acciones que desea deshacer. Asegúrese de seleccionar los elementos que tienen el mismo tipo de acción. Se abre un panel desplegable.
3. En el panel desplegable, seleccione **Deshacer**.

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Para quitar un archivo de la cuarentena en varios dispositivos 

1. Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e inicie sesión.
2. En la **pestaña Historial,** seleccione un elemento que tenga el tipo de acción **Archivo de cuarentena**.
3. En el panel desplegable, seleccione **Aplicar a X más** instancias de este archivo y, a continuación, seleccione **Deshacer**.

## <a name="automation-levels-automated-investigation-results-and-resulting-actions"></a>Niveles de automatización, resultados de investigación automatizados y acciones resultantes

Los niveles de automatización afectan a si determinadas acciones de corrección se toman automáticamente o solo después de su aprobación. A veces, el equipo de operaciones de seguridad tiene que seguir más pasos, según los resultados de una investigación automatizada. En la tabla siguiente se resumen los niveles de automatización, los resultados de las investigaciones automatizadas y qué hacer en cada caso. 

|Configuración del grupo de dispositivos | Resultados de la investigación automatizada | Qué hacer |
|:---|:---|:---|
|**Completa: corregir las amenazas automáticamente** (la configuración recomendada) |Se alcanza un veredicto de malintencionado para obtener una prueba.  <br/><br/>Las acciones de corrección apropiadas se toman automáticamente. |[Revisar acciones completadas](#review-completed-actions) |
|**Completa: corregir las amenazas automáticamente** |Se alcanza un veredicto *de Sospechoso* para obtener una prueba. <br/><br/>Las acciones de corrección están pendientes de aprobación para continuar. | [Aprobar (o rechazar) acciones pendientes](#review-pending-actions) |
|**Semi: requerir aprobación para cualquier corrección**  |Se alcanza un veredicto *de malintencionado*  o sospechoso para obtener una prueba. <br/><br/>Las acciones de corrección están pendientes de aprobación para continuar.  |[Aprobar (o rechazar) acciones pendientes](#review-pending-actions) |
|**Semi: requerir aprobación para la corrección de carpetas principales** |Se alcanza un veredicto de malintencionado para obtener una prueba.  <br/><br/>Si el artefacto es un archivo o ejecutable y se encuentra en un directorio del sistema operativo, como la carpeta Windows o la carpeta Archivos de programa, las acciones de corrección están pendientes de aprobación. <br/><br/>Si el artefacto no *está en* un directorio del sistema operativo, las acciones de corrección se toman automáticamente. |1. [Aprobar (o rechazar) acciones pendientes](#review-pending-actions)<br/><br/>2. [Revisar las acciones completadas](#review-completed-actions) |
|**Semi: requerir aprobación para la corrección de carpetas principales** |Se alcanza un veredicto *de Sospechoso* para obtener una prueba. <br/><br/>Las acciones de corrección están pendientes de aprobación.  |[Aprobar (o rechazar) acciones pendientes](#review-pending-actions).|
|**Semi: requerir aprobación para la corrección de carpetas no temporales** |Se alcanza un veredicto de malintencionado para obtener una prueba.  <br/><br/>Si el artefacto es un archivo o ejecutable que no está en una carpeta temporal, como la carpeta de descargas del usuario o la carpeta temporal, las acciones de corrección están pendientes de aprobación. <br/><br/>Si el artefacto es un archivo o ejecutable *que se encuentra* en una carpeta temporal, las acciones de corrección se toman automáticamente.  |1. [Aprobar (o rechazar) acciones pendientes](#review-pending-actions)<br/><br/>2. [Revisar las acciones completadas](#review-completed-actions)  |
|**Semi: requerir aprobación para la corrección de carpetas no temporales** |Se alcanza un veredicto *de Sospechoso* para obtener una prueba. <br/><br/>Las acciones de corrección están pendientes de aprobación. |[Aprobar (o rechazar) acciones pendientes](#review-pending-actions)  | 
|Cualquiera de los **niveles de automatización** completa **o** semi |Un veredicto *de No se han encontrado amenazas* se alcanza para obtener una prueba. <br/><br/>No se han realizado acciones de corrección y no hay ninguna acción pendiente de aprobación. |[Ver detalles y resultados de las investigaciones automatizadas](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center) |
|**Sin respuesta automatizada** (no recomendada)|No se ejecutan investigaciones automatizadas, por lo que no se alcanzan los veredictos y no se toman medidas de corrección ni se espera su aprobación. |[Considera la posibilidad de configurar o cambiar los grupos de dispositivos para usar **la automatización** completa **o** semi](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) |

En Microsoft Defender para endpoint, se realiza un seguimiento de todos los veredictos en el [Centro de acciones](auto-investigation-action-center.md#new-a-unified-action-center).

## <a name="next-steps"></a>Pasos siguientes

- [Obtenga información sobre las capacidades de respuesta en directo](live-response.md)
- [Búsqueda proactiva de amenazas con búsqueda avanzada](advanced-hunting-overview.md)
- [Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión](defender-endpoint-false-positives-negatives.md)

## <a name="see-also"></a>Vea también

- [Información general sobre las investigaciones automatizadas](automated-investigations.md)
