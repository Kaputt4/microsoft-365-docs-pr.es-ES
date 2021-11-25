---
title: Propiedades y métodos de la actividad de corrección
description: La respuesta de la API contiene amenazas & administración de vulnerabilidades de corrección creadas en el espacio empresarial. Puede solicitar todas las actividades de corrección, solo una actividad de corrección o información sobre los dispositivos expuestos para una tarea de corrección seleccionada.
keywords: apis, remediation, remediation api, get, remediation tasks, remediation methods, remediation properties,
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: cbd37d48477cdd9b0a0dc7c6c5703b96ffb4b89e
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168587"
---
# <a name="remediation-activity-methods-and-properties"></a>Propiedades y métodos de la actividad de corrección

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!Include[Prerelease information](../../includes/prerelease.md)]

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

La respuesta de la API contiene [& administración de vulnerabilidades](next-gen-threat-and-vuln-mgt.md)   de corrección de amenazas que se han creado en el espacio empresarial.

## <a name="methods"></a>Methods

Método|Tipo de datos|Description
:---|:---|:---
[Enumerar todas las actividades de corrección](get-remediation-all-activities.md)|Colección Investigation|Devuelve información sobre todas las actividades de corrección.
[Lista de dispositivos expuestos de una actividad de corrección](get-remediation-exposed-devices-activities.md)|Entidad de investigación|Devuelve información sobre los dispositivos expuestos para la actividad de corrección especificada.
[Obtener una actividad de corrección de acuerdo con su id](get-remediation-one-activity.md)|Entidad de investigación|Devuelve información sobre la actividad de corrección especificada.

Obtenga más información sobre [las actividades de corrección](tvm-remediation.md).

## <a name="properties"></a>Propiedades

Id. de propiedad|Tipo de datos|Description
:---|:---|:---
Categoría|Cadena|Categoría de la actividad de corrección (configuración software/seguridad)
completerEmail|Cadena|Si alguien completó manualmente la actividad de corrección, esta columna contiene su correo electrónico
completerId|Cadena|Si alguien completó manualmente la actividad de corrección, esta columna contiene su identificador de objeto.
completionMethod|Cadena|Una actividad de corrección se puede completar "automáticamente" (si todos los dispositivos están parcheados) o "manualmente" por una persona que selecciona "marcar como completada".
createdOn|DateTime|Hora en que se creó esta actividad de corrección
Descripción|Cadena|Descripción de esta actividad de corrección
dueOn|DateTime|Fecha de vencimiento que el creador estableció para esta actividad de corrección
fixedDevices||Número de dispositivos que se han corregido
Id.|Cadena|Identificador de esta actividad de corrección
nameId|Cadena|Nombre del producto relacionado
Prioridad|Cadena|Prioridad del conjunto de creadores para esta actividad de corrección (High\Medium\Low)
productId|Cadena|Id. de producto relacionado
productivityImpactRemediationType|Cadena|Solo se podrían solicitar algunos cambios de configuración para dispositivos que no afecten a los usuarios. Este valor indica la selección entre "todos los dispositivos expuestos" o "solo dispositivos sin impacto del usuario".
rbacGroupNames|Cadena|Nombres de grupo de dispositivos relacionados
recommendedProgram|Cadena|Programa recomendado para actualizar a
recommendedVendor|Cadena|Proveedor recomendado para actualizar a
recommendedVersion|Cadena|Versión recomendada para actualizar o actualizar a
relatedComponent|Cadena|Componente relacionado de esta actividad de corrección (similar al componente relacionado para una recomendación de seguridad)
requesterEmail|Cadena|Dirección de correo electrónico del creador
requesterId|Cadena|Id. de objeto Creator
requesterNotes|Cadena|Las notas (texto libre) que el creador agregó para esta actividad de corrección
Scid|Cadena|SCID de la recomendación de seguridad relacionada
Estado|Cadena|Estado de la actividad de corrección (Activo/Completado)
statusLastModifiedOn|DateTime|Fecha en la que se actualizó el campo de estado
targetDevices|Long|Número de dispositivos expuestos a los que se aplica esta corrección
Título|Cadena|Título de esta actividad de corrección
Tipo|Cadena|Tipo de corrección
vendorId|Cadena|Nombre de proveedor relacionado

## <a name="see-also"></a>Recursos adicionales

- [Obtener una actividad de corrección de acuerdo con su id](get-remediation-one-activity.md)

- [Enumerar todas las actividades de corrección](get-remediation-all-activities.md)

- [Lista de dispositivos expuestos de una actividad de corrección](get-remediation-exposed-devices-activities.md)

- [Amenazas basadas en riesgos & administración de vulnerabilidades](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilidades de la organización](tvm-weaknesses.md)
