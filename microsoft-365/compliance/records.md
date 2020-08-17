---
title: Obtenga más información sobre los registros
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Obtenga información acerca de los registros para que pueda implementar la solución de administración de registros de Microsoft 365.
ms.openlocfilehash: e64e91aeef307d05f23c47987a84baaf386324df
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685446"
---
# <a name="learn-about-records"></a>Obtenga más información sobre los registros

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

La administración de registros de Microsoft 365 ayuda a su organización a cumplir con las directivas corporativas y las obligaciones legales o reglamentarias, al mismo tiempo que reduce el riesgo y la responsabilidad legal.

Cuando el contenido está marcado como un registro:

- Se colocan restricciones en los elementos relativas a qué [acciones se permiten o se bloquean](#compare-restrictions-for-what-actions-are-allowed-or-blocked).

- Se registran otras actividades sobre el elemento.

- Tendrá la prueba de la eliminación cuando se eliminen los elementos al final de su período de retención.

Puede usar las [etiquetas de retención](retention.md#retention-labels) para marcar el contenido como un registro. Puede publicar esas etiquetas de modo que los usuarios y administradores puedan aplicarlas manualmente al contenido o aplicarlas automáticamente al contenido que desee marcar como registro.

Al usar las etiquetas de retención para marcar contenido como registros, puede implementar una sola estrategia de administración de registros uniforme en todo el entorno de Microsoft 365.

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>Comparar restricciones de acciones permitidas o bloqueadas

Use la tabla siguiente para identificar qué restricciones se colocan en el contenido como resultado de aplicar una etiqueta de retención estándar y conocer las etiquetas de retención que marcan el contenido como un registro. 

Una etiqueta de retención estándar tiene la configuración para conservar datos sin marcar el contenido como un registro.

>[!NOTE] 
> Por motivos de integridad, la tabla contiene columnas para un registro bloqueado y desbloqueado, lo que se aplica a SharePoint y OneDrive, pero no a Exchange. La capacidad de bloquear y desbloquear un registro usa el [control de versiones de registros](record-versioning.md) que no es compatible con los elementos de Exchange. Por lo tanto, para todos los elementos de Exchange que estén marcados como un registro, el comportamiento que se asigna a la columna **registro bloqueado** y a la columna **registro desbloqueado** no es relevante.


|Acción| Etiqueta de retención |Registro: bloqueado| Registro: desbloqueado|
|:-----|:-----|:-----|:-----|:-----|
|Editar contenidos|Permitido | **Bloqueado** | Permitido|
|Editar propiedades, incluido cambiar nombre|Permitido |Permitido | Permitido|
|Eliminar|Permitido<sup>1</sup> |**Bloqueado** | **Bloqueado**|
|Copiar|Permitido |Permitido | Permitido|
|Moverse dentro del contenedor<sup>2</sup>|Permitido |Permitido | Permitido|
|Moverse entre contenedores<sup>2</sup>|Permitido |Permitido si nunca se desbloquea | Permitido|
|Abrir y leer|Permitido |Permitido | Permitido|
|Cambiar etiqueta|Permitido |Permitido: solo administradores del contenedor | Permitido: solo administradores del contenedor|
|Quitar etiqueta|Permitido |Permitido: solo administradores del contenedor | Permitido: solo administradores del contenedor|

Notas al pie:

<sup>1</sup> Compatible con OneDrive y Exchange reteniendo una copia en una ubicación segura, pero bloqueado por SharePoint.

Mensaje que ve el usuario si intenta eliminar un documento con etiquetas en SharePoint:

![Mensaje que indica que el elemento no se elimina de SharePoint](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<sup>2</sup> Los contenedores incluyen librerías de documentos de SharePoint y buzones de Exchange.

## <a name="next-steps"></a>Pasos siguientes

Si aún no tiene etiquetas de retención que se usarán para la administración de registros, consulte [Introducción a las directivas y las etiquetas de retención](get-started-with-retention.md).

Para marcar el contenido como un registro, vea [Declarar registros con las etiquetas de retención](declare-records.md).
