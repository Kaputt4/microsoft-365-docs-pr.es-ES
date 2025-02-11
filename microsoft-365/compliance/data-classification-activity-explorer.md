---
title: Introducción al Explorador de actividades
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
- tier1
- purview-compliance
- m365solution-mip
- m365initiative-compliance
- highpri
search.appverid:
- MOE150
- MET150
description: El Explorador de actividades le permite ver y filtrar las acciones que los usuarios están realizando en el contenido etiquetado.
ms.openlocfilehash: fd537c4157347a2984af0c1fa2097278abadd6a8
ms.sourcegitcommit: 21548843708d80bc861f03ffae41457252492bb6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2022
ms.locfileid: "68793772"
---
# <a name="get-started-with-activity-explorer"></a>Introducción al explorador de actividad

La [información general de clasificación de datos](data-classification-overview.md) y las pestañas [del explorador de contenido](data-classification-content-explorer.md) proporcionan visibilidad sobre qué contenido se ha detectado y etiquetado y dónde está ese contenido. [El explorador de actividad](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer) redondea este conjunto de funciones al permitirle supervisar lo que se está haciendo con el contenido etiquetado. El Explorador de actividades proporciona una vista histórica de las actividades en el contenido etiquetado. La información de actividad se recopila de los registros de auditoría unificados de Microsoft 365, se transforma y está disponible en la interfaz de usuario del Explorador de actividad. El explorador de actividad informa de datos de hasta 30 días.

![Explorador de actividad de información general de la captura de pantalla del marcador de posición.](../media/data-classification-activity-explorer-1.png)

Hay más de 30 filtros diferentes disponibles, estos son algunos:

- Intervalo de fechas
- Tipo de actividad
- Ubicación
- User
- Etiqueta de confidencialidad
- Etiqueta de retención
- Ruta de acceso de archivo
- Directiva DLP



[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="prerequisites"></a>Requisitos previos

Todas las cuentas que tengan acceso a la clasificación de datos y la usen deben tener una licencia asignada de una de estas suscripciones:

- Microsoft 365 (E5)
- Office 365 (E5)
- Complemento de cumplimiento avanzado (E5)
- Complemento de inteligencia de amenazas avanzado (E5)
- Gobernanza y protección de la información de Microsoft 365 E5/A5
- Cumplimiento de Microsoft 365 E5/A5 

### <a name="permissions"></a>Permisos

Una cuenta debe tener asignada explícitamente la pertenencia a cualquiera de estos grupos de roles o conceder explícitamente el rol.

### <a name="roles-and-role-groups"></a>Roles y grupos de roles

Hay roles y grupos de roles que puede usar para ajustar los controles de acceso.

Esta es una lista de los roles aplicables que puede usar. Para obtener más información sobre ellos, consulte [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md).

- Administrador de Information Protection
- Analista de Information Protection
- Investigador de protección de información
- Lector de protección de información

Esta es una lista de los grupos de roles aplicables que puede usar. Para obtener más información sobre, consulte [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md).

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

**Roles de Microsoft 365**

- Administrador de cumplimiento
- Administrador de seguridad
- Lector de seguridad

## <a name="activity-types"></a>Tipos de actividad

El Explorador de actividades recopila información de actividad de los registros de auditoría en varios orígenes de actividades. Para obtener información más detallada sobre qué actividad de etiquetado hace que sea para el Explorador de actividad, vea [Eventos de etiquetado disponibles en el Explorador de actividad](data-classification-activity-explorer-available-events.md).

**Actividades de etiqueta de confidencialidad** y **actividades de etiquetado de retención** de aplicaciones nativas de Office, el cliente y escáner de etiquetado unificado de Azure Information Protection (AIP), SharePoint Online, Exchange Online (solo etiquetas de confidencialidad) y OneDrive. Por ejemplo:

- Etiqueta aplicada
- Etiqueta cambiada (actualizada, degradada o eliminada)
- Simulación de etiquetado automático
- Archivo leído

**Analizador de Azure Information Protection (AIP) y clientes de AIP**

- Protección aplicada
- Protección cambiada
- Protección eliminada
- Archivos detectados

El Explorador de actividades también recopila eventos de **coincidencias** de directiva DLP de Exchange Online, SharePoint Online, OneDrive, Chat y canal de Teams (versión preliminar), carpetas y bibliotecas locales de SharePoint, recursos compartidos de archivos locales y dispositivos de Windows 10 a través de **prevención de pérdida de datos de punto de conexión (DLP).** Algunos ejemplos de eventos de Windows 10 dispositivos son archivos:

- Eliminaciones
- Creaciones
- Copiada en el Portapapeles
- Modified
- Lectura
- Impreso
- Retitulado
- Copiado en el recurso compartido de red
- Acceso mediante una aplicación no permitida 

Comprender qué acciones se realizan con el contenido etiquetado confidencial le ayuda a ver si los controles que tiene en su lugar, como las directivas [de Prevención de pérdida de datos de Microsoft Purview](dlp-learn-about-dlp.md) son eficaces o no. Si no es así, o si se detecta algo inesperado, como un gran número de elementos etiquetados `highly confidential`y se degradan`general`, puede administrar las distintas directivas y llevar a cabo nuevas acciones para restringir el comportamiento no deseado.

> [!NOTE]
> El explorador de actividad no supervisa actualmente las actividades de retención de Exchange Online.

## <a name="see-also"></a>Recursos adicionales

- [Información sobre las etiquetas de confidencialidad](sensitivity-labels.md)
- [Más información sobre las directivas y las etiquetas de retención](retention.md)
- [Obtener más información acerca de los tipos de información confidencial](sensitive-information-type-learn-about.md)
- [Obtenga información sobre la clasificación de datos](data-classification-overview.md)
