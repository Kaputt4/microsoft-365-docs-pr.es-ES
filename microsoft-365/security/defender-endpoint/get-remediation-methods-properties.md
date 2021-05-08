---
title: Propiedades y métodos de actividad de corrección
description: La respuesta de la API contiene amenazas & administración de vulnerabilidades de corrección creadas en el espacio empresarial. Puede solicitar todas las actividades de corrección, solo una actividad de corrección o información sobre los dispositivos expuestos para una tarea de corrección seleccionada.
keywords: apis, remediation, remediation api, get, remediation tasks, remediation methods, remediation properties,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4c0ecd89c45ec2c91dc37f0c9cd0bfb868c0474e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245545"
---
# <a name="remediation-activity-methods-and-properties"></a>Propiedades y métodos de actividad de corrección

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

La respuesta de la API contiene [& administración de vulnerabilidades](next-gen-threat-and-vuln-mgt.md)   de corrección de amenazas que se han creado en el espacio empresarial.  

## <a name="methods"></a>Métodos

Método | Tipo de datos | Descripción
:---|:---|:---
[Enumerar todas las actividades de corrección](get-remediation-all-activities.md) | Colección Investigation | Devuelve información sobre todas las actividades de corrección.
[Lista de dispositivos expuestos de una actividad de corrección](get-remediation-exposed-devices-activities.md) | Entidad de investigación | Devuelve información sobre los dispositivos expuestos para la actividad de corrección especificada.
[Obtener una actividad de corrección por id.](get-remediation-one-activity.md) | Entidad de investigación | Devuelve información sobre la actividad de corrección especificada.

Obtenga más información sobre [las actividades de corrección](tvm-remediation.md).

## <a name="properties"></a>Propiedades

Id. de propiedad | Tipo de datos | Descripción
:---|:---|:---
categoría | Cadena | Categoría de la actividad de corrección (configuración software/seguridad)
completerEmail | Cadena | Si alguien completó manualmente la actividad de corrección, esta columna contiene su correo electrónico
completerId | Cadena | Si alguien completó la actividad de corrección manualmente, esta columna contiene su identificador de objeto
completionMethod | Cadena | Una actividad de corrección se puede completar "automáticamente" (si todos los dispositivos están parcheados) o "manualmente" por una persona que selecciona "marcar como completada".
createdOn | DateTime | Hora en que se creó esta actividad de corrección
description | Cadena | Descripción de esta actividad de corrección
dueOn | DateTime | Fecha de vencimiento que el creador estableció para esta actividad de corrección
fixedDevices |  | Número de dispositivos que se han corregido
id | Cadena | Identificador de esta actividad de corrección
nameId | Cadena | Nombre del producto relacionado
priority | Cadena | Prioridad del conjunto de creadores para esta actividad de corrección (High\Medium\Low)
productId | Cadena | Id. de producto relacionado
productivityImpactRemediationType | Cadena | Solo se podrían solicitar algunos cambios de configuración para dispositivos sin impacto del usuario. Este valor indica la selección entre "todos los dispositivos expuestos" o "solo dispositivos sin impacto del usuario".
rbacGroupNames | Cadena | Nombres de grupo de dispositivos relacionados
recommendedProgram | Cadena | Programa recomendado para actualizar a
recommendedVendor | Cadena | Proveedor recomendado para actualizar a
recommendedVersion | Cadena | Versión recomendada para actualizar o actualizar a
relatedComponent | Cadena | Componente relacionado de esta actividad de corrección (similar al componente relacionado para una recomendación de seguridad)
requesterEmail | Cadena | Dirección de correo electrónico del creador
requesterId | Cadena | Id. de objeto Creator
requesterNotes | Cadena | Las notas (texto libre) que el creador agregó para esta actividad de corrección
scid | Cadena | SCID de la recomendación de seguridad relacionada
status | Cadena | Estado de la actividad de corrección (Activo/Completado)
statusLastModifiedOn | DateTime | Fecha en la que se actualizó el campo de estado
targetDevices | Long | Número de dispositivos expuestos a los que se aplica esta corrección
title | Cadena | Título de esta actividad de corrección
type | Cadena | Tipo de corrección
vendorId | Cadena | Nombre de proveedor relacionado

## <a name="see-also"></a>Vea también

- [Obtener una actividad de corrección por id.](get-remediation-one-activity.md)

- [Enumerar todas las actividades de corrección](get-remediation-all-activities.md)

- [Lista de dispositivos expuestos de una actividad de corrección](get-remediation-exposed-devices-activities.md)

- [Amenazas basadas en riesgos & administración de vulnerabilidades](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilidades de la organización](tvm-weaknesses.md)
