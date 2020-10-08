---
title: Introducción al explorador de actividad
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: El explorador de actividad complementa la funcionalidad de la característica de clasificación de datos permitiéndole ver y filtrar las acciones que los usuarios están realizando en el contenido etiquetado.
ms.openlocfilehash: 0175f41ca3fbcfc685acf933cc0cd97af6aa61ad
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379199"
---
# <a name="get-started-with-activity-explorer"></a>Introducción al explorador de actividad

La descripción general de la clasificación de datos y las pestañas del explorador de contenido le ofrecen visibilidad sobre el contenido que se ha descubierto y etiquetado, y dónde está ese contenido. El explorador de actividad complementa este conjunto de funciones permitiéndole supervisar lo que se lleva a cabo con el contenido de la etiqueta. El explorador de actividad ofrece una vista histórica.

![Marcador de posición captura de pantalla información general explorador de actividad](../media/data-classification-activity-explorer-1.png)

Hay más de 30 filtros diferentes disponibles, estos son algunos:

- Intervalo de fechas:
- TIPO DE ACTIVIDAD
- Ubicación
- Usuario
- Etiqueta de confidencialidad
- Etiqueta de retención:
- ruta de acceso del archivo
- Directiva DLP


## <a name="prerequisites"></a>Requisitos previos

Todas las cuentas que tengan acceso a la clasificación de datos y la usen deben tener una licencia asignada de una de estas suscripciones:

- Microsoft 365 (E5)
- Office 365 (E5)
- Complemento de cumplimiento avanzado (E5)
- Complemento de inteligencia de amenazas avanzado (E5)

### <a name="permissions"></a>Permisos

 Para obtener acceso a la pestaña del explorador de actividad, una cuenta debe tener asignada una suscripción en cualquiera de estos roles o grupos de roles.

**Grupos de roles de Microsoft 365**

- Administrador global
- Administrador de cumplimiento
- Administrador de seguridad
- Administrador de datos de cumplimiento

## <a name="activity-type"></a>Tipo de actividad

Microsoft 365 supervisa y realiza un seguimiento de los tipos de actividades en SharePoint Online y OneDrive, como:

- etiqueta aplicada
- etiqueta cambiada (actualizada, degradada o eliminada)
- simulación de etiquetado automático

El valor de comprensión de las acciones que se toman con el contenido identificado por la etiqueta es que puede ver si los controles que ya se han puesto en su sitio, como [Directivas de prevención de pérdida de datos](data-loss-prevention-policies.md) son efectivas o no. Si no es así, o si se detecta algo inesperado, como un gran número de elementos etiquetados `highly confidential`y se degradan`general`, puede administrar las distintas directivas y llevar a cabo nuevas acciones para restringir el comportamiento no deseado.

> [!NOTE]
> El explorador de actividad no supervisa actualmente las actividades de retención de Exchange Online.

## <a name="see-also"></a>Recursos adicionales
- [Más información sobre las etiquetas de confidencialidad](sensitivity-labels.md)
- [Más información sobre las directivas y las etiquetas de retención](retention.md)
- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)

