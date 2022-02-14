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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: El explorador de actividades le permite ver y filtrar las acciones que los usuarios están llevando a cabo en el contenido etiquetado.
ms.openlocfilehash: 93cd3910a79b136d95ba46fa79940d379340cf75
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2022
ms.locfileid: "62806569"
---
# <a name="get-started-with-activity-explorer"></a>Introducción al explorador de actividad

La [introducción a la](data-classification-overview.md) clasificación de datos y las pestañas del [explorador](data-classification-content-explorer.md) de contenido le dan visibilidad sobre qué contenido se ha detectado y etiquetado, y dónde está ese contenido. El explorador de actividad complementa este conjunto de funciones permitiéndole supervisar lo que se lleva a cabo con el contenido de la etiqueta. El explorador de actividades proporciona una vista histórica de las actividades en el contenido etiquetado. La información de actividad se recopila Microsoft 365 registros de auditoría unificados, transformados y puestos a disposición en la interfaz de usuario del explorador de actividades. El explorador de actividades informa sobre datos de hasta 30 días.

![Explorador de actividades de información general de captura de pantalla de marcador de posición.](../media/data-classification-activity-explorer-1.png)

Hay más de 30 filtros diferentes disponibles, estos son algunos:

- Intervalo de fechas
- Tipo de actividad
- Ubicación
- User
- Etiqueta de confidencialidad
- Etiqueta de retención
- Ruta de acceso de archivo
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

Una cuenta debe tener asignada de forma explícita la pertenencia a cualquiera de estos grupos de roles o concederla explícitamente.

### <a name="roles-and-role-groups-in-preview"></a>Roles y grupos de roles en la versión preliminar

Hay roles y grupos de roles en versión preliminar que puede probar para ajustar los controles de acceso.

Aquí tiene una lista de roles Microsoft Information Protection (MIP) que están en la versión preliminar. Para obtener más información, consulte [Roles en el Centro de seguridad y cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)

- Administrador de Information Protection
- Analista de Information Protection
- Investigador de protección de información
- Lector de protección de información

Aquí tiene una lista de grupos de roles de MIP que están en la versión preliminar. Para obtener más información, consulte [Grupos de roles en el Centro de seguridad y cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#role-groups-in-the-security--compliance-center)

- Protección de la información
- Administradores de Information Protection
- Analistas de Information Protection
- Investigadores de Information Protection
- Lectores de Information Protection

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
- Lector de seguridad

## <a name="activity-types"></a>Tipos de actividad

El explorador de actividades recopila información de actividad de los registros de auditoría en varios orígenes de actividades. Para obtener información más detallada sobre qué actividad de etiquetado hace que esté en el Explorador de actividades, vea [Labeling events available in Activity explorer](data-classification-activity-explorer-available-events.md).

**Actividades de** etiquetas  de confidencialidad y actividades de etiquetado de retención de aplicaciones nativas de Office, complemento de Azure Information Protection, SharePoint Online, Exchange Online (solo etiquetas de confidencialidad) y OneDrive. Por ejemplo:

- Etiqueta aplicada
- Etiqueta cambiada (actualizada, degradada o eliminada)
- Simulación de etiquetado automático
- Archivo leído

**Escáner de Azure Information Protection (AIP) y clientes AIP**

- Protección aplicada
- Protección modificada
- Protección eliminada
- Archivos detectados

El explorador de actividades también recopila eventos de coincidencias de directivas **DLP** de Exchange Online, SharePoint Online, OneDrive, chat y canal de Teams (versión preliminar), carpetas y bibliotecas locales de SharePoint y recursos compartidos de archivos locales y dispositivos Windows 10 **a través de Prevención de pérdida de datos de extremo (DLP).** Algunos ejemplos de eventos de Windows 10 dispositivos son archivos:

- Eliminaciones
- Creaciones
- Copiada en el Portapapeles
- Modified
- Lectura
- Impreso
- Renamed
- Copiado en el recurso compartido de red
- Acceso a través de una aplicación sin alambrar 

Comprender qué acciones se están haciendo con el contenido etiquetado confidencial le ayuda a ver si los controles que tiene en su lugar, como las directivas de prevención de pérdida de datos son [efectivos](dlp-learn-about-dlp.md) o no. Si no es así, o si se detecta algo inesperado, como un gran número de elementos etiquetados `highly confidential`y se degradan`general`, puede administrar las distintas directivas y llevar a cabo nuevas acciones para restringir el comportamiento no deseado.

> [!NOTE]
> El explorador de actividad no supervisa actualmente las actividades de retención de Exchange Online.

## <a name="see-also"></a>Recursos adicionales

- [Información sobre las etiquetas de confidencialidad](sensitivity-labels.md)
- [Más información sobre las directivas y las etiquetas de retención](retention.md)
- [Obtener más información acerca de los tipos de información confidencial](sensitive-information-type-learn-about.md)
- [Obtenga información sobre la clasificación de datos](data-classification-overview.md)
