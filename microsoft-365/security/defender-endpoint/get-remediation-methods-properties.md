---
title: Propiedades y métodos de la actividad de corrección
description: La respuesta de LA API contiene actividades de corrección de amenazas & administración de vulnerabilidades creadas en el inquilino. Puede solicitar todas las actividades de corrección, solo una actividad de corrección o información sobre los dispositivos expuestos para una tarea de corrección seleccionada.
keywords: apis, remediation, remediation api, get, remediation tasks, remediation methods, remediation properties,
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 14f57d6590d580e0145abc2da788f184c88a721e
ms.sourcegitcommit: a7cd723fd62b4b0aae9c2c2df04ead3c28180084
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2022
ms.locfileid: "65840263"
---
# <a name="remediation-activity-methods-and-properties"></a>Propiedades y métodos de la actividad de corrección

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!Include[Prerelease information](../../includes/prerelease.md)]

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

La respuesta de API contiene las actividades de corrección [de amenazas & administración de vulnerabilidades](next-gen-threat-and-vuln-mgt.md) que se han creado en el inquilino.

## <a name="methods"></a>Métodos

Método|Tipo de datos|Descripción
:---|:---|:---
[Enumerar todas las actividades de corrección](get-remediation-all-activities.md)|Colección de investigación|Devuelve información sobre todas las actividades de corrección.
[Lista de dispositivos expuestos de una actividad de corrección](get-remediation-exposed-devices-activities.md)|Entidad de investigación|Devuelve información sobre los dispositivos expuestos para la actividad de corrección especificada.
[Obtener una actividad de corrección de acuerdo con su id](get-remediation-one-activity.md)|Entidad de investigación|Devuelve información para la actividad de corrección especificada.

Obtenga más información sobre [las actividades de corrección](tvm-remediation.md).

## <a name="properties"></a>Propiedades

Id. de propiedad|Tipo de datos|Descripción
:---|:---|:---
Categoría|Cadena|Categoría de la actividad de corrección (configuración de software/seguridad)
completerEmail|Cadena|Si alguien completó manualmente la actividad de corrección, esta columna contiene su correo electrónico.
completerId|Cadena|Si alguien completó manualmente la actividad de corrección, esta columna contiene su identificador de objeto.
completionMethod|Cadena|Una actividad de corrección se puede completar "automáticamente" (si todos los dispositivos están revisados) o "manualmente" por una persona que selecciona "marcar como completado".
createdOn|DateTime|Hora en que se creó esta actividad de corrección
Descripción|Cadena|Descripción de esta actividad de corrección
dueOn|DateTime|Fecha de vencimiento establecida por el creador para esta actividad de corrección
fixedDevices||Número de dispositivos que se han corregido
ID|Cadena|Identificador de esta actividad de corrección
nameId|Cadena|Nombre del producto relacionado
Prioridad|Cadena|Prioridad del creador establecido para esta actividad de corrección (Alto\Medio\Bajo)
Productid|Cadena|Identificador de producto relacionado
productivityImpactRemediationType|Cadena|Solo se pueden solicitar algunos cambios de configuración para los dispositivos que no afectan a los usuarios. Este valor indica la selección entre "todos los dispositivos expuestos" o "solo los dispositivos sin ningún impacto en el usuario".
rbacGroupNames|Cadena|Nombres de grupos de dispositivos relacionados
recommendedProgram|Cadena|Programa recomendado para actualizar a
recommendedVendor|Cadena|Proveedor recomendado para actualizar a
recommendedVersion|Cadena|Versión recomendada para actualizar o actualizar a
relatedComponent|Cadena|Componente relacionado de esta actividad de corrección (similar al componente relacionado para una recomendación de seguridad)
requesterEmail|Cadena|Dirección de correo electrónico de Creator
requesterId|Cadena|Identificador de objeto de Creator
requesterNotes|Cadena|Las notas (texto libre) que el creador agregó para esta actividad de corrección
Scid|Cadena|SCID de la recomendación de seguridad relacionada
Estado|Cadena|Estado de la actividad de corrección (activo/completado)
statusLastModifiedOn|DateTime|Fecha en que se actualizó el campo de estado
targetDevices|Long|Número de dispositivos expuestos a los que se aplica esta corrección
Título|Cadena|Título de esta actividad de corrección
Tipo|Cadena|Tipo de corrección
vendorId|Cadena|Nombre del proveedor relacionado

## <a name="see-also"></a>Consulte también

- [Obtener una actividad de corrección de acuerdo con su id](get-remediation-one-activity.md)

- [Enumerar todas las actividades de corrección](get-remediation-all-activities.md)

- [Lista de dispositivos expuestos de una actividad de corrección](get-remediation-exposed-devices-activities.md)

- [& administración de vulnerabilidades de amenazas basadas en riesgos](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilidades en la organización](tvm-weaknesses.md)
