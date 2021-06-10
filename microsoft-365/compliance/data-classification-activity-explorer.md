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
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: El explorador de actividad complementa la funcionalidad de la característica de clasificación de datos permitiéndole ver y filtrar las acciones que los usuarios están realizando en el contenido etiquetado.
ms.openlocfilehash: 414ef4e5d9f6472180a5eaef391d3eba33463b02
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114012"
---
# <a name="get-started-with-activity-explorer"></a>Introducción al explorador de actividad

La [introducción a la](data-classification-overview.md) clasificación de datos y las pestañas del [explorador](data-classification-content-explorer.md) de contenido le dan visibilidad sobre qué contenido se ha detectado y etiquetado, y dónde está ese contenido. El explorador de actividad complementa este conjunto de funciones permitiéndole supervisar lo que se lleva a cabo con el contenido de la etiqueta. El explorador de actividades proporciona una vista histórica de las actividades en el contenido etiquetado. La información de actividad se recopila Microsoft 365 registros de auditoría unificados, transformados y puestos a disposición en la interfaz de usuario del explorador de actividades. 

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
- Gobernanza y protección de la información de Microsoft 365 E5/A5
- Cumplimiento de Microsoft 365 E5/A5 

### <a name="permissions"></a>Permisos

 Para obtener acceso a la pestaña explorador de actividades, se debe asignar explícitamente la pertenencia a una cuenta en cualquiera de estos grupos de roles o concederla explícitamente.

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

**Grupos de roles de Microsoft 365**

- Administrador global
- Administrador de cumplimiento
- Administrador de seguridad
- Administrador de datos de cumplimiento

**Microsoft 365 roles**

- Administrador de cumplimiento
- Administrador de seguridad

## <a name="activity-types"></a>Tipos de actividad

El explorador de actividades recopila información de actividad de los registros de auditoría en varios orígenes de actividades. Para obtener información más detallada sobre qué actividad de etiquetado la convierte en explorador de actividades, vea [Labeling events available in Activity explorer](data-classification-activity-explorer-available-events.md).

**Actividades de etiquetas** de confidencialidad y actividades de etiquetado de retención de aplicaciones nativas de Office, complemento de Azure Information Protection, SharePoint Online, Exchange Online (solo etiquetas de confidencialidad) y OneDrive.  Por ejemplo:

- etiqueta aplicada
- etiqueta cambiada (actualizada, degradada o eliminada)
- simulación de etiquetado automático
- archivo leído 

**Escáner de Azure Information Protection (AIP) y clientes AIP**

- protección aplicada
- protección modificada
- protección eliminada
- archivos detectados 

El explorador de actividades también recopila eventos de coincidencias de directivas **DLP** de Exchange Online, SharePoint Online, OneDrive, chat y canal de Teams (versión preliminar), carpetas y bibliotecas de SharePoint locales y recursos compartidos de archivos locales y dispositivos Windows 10 mediante prevención de pérdida de datos de extremo **(DLP).** Algunos ejemplos de eventos de Windows 10 dispositivos son archivos:

- eliminaciones
- creaciones
- copiado en el Portapapeles
- modificado 
- read
- impreso
- nombre cambiado
- copiado en el recurso compartido de red
- a la que se accede mediante una aplicación sin alambrar 

El valor de comprender qué acciones se están haciendo con el contenido etiquetado confidencial es que puede ver si los controles que ya ha puesto en marcha, como la prevención de pérdida de datos son [efectivos](dlp-learn-about-dlp.md) o no. Si no es así, o si se detecta algo inesperado, como un gran número de elementos etiquetados `highly confidential`y se degradan`general`, puede administrar las distintas directivas y llevar a cabo nuevas acciones para restringir el comportamiento no deseado.

> [!NOTE]
> El explorador de actividad no supervisa actualmente las actividades de retención de Exchange Online.

## <a name="see-also"></a>Recursos adicionales

- [Información sobre las etiquetas de confidencialidad](sensitivity-labels.md)
- [Más información sobre las directivas y las etiquetas de retención](retention.md)
- [Obtener más información acerca de los tipos de información confidencial](sensitive-information-type-learn-about.md)
- [Obtenga información sobre la clasificación de datos.](data-classification-overview.md)
