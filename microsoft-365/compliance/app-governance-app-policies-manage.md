---
title: Administrar directivas de aplicación
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Administre las directivas de gobernanza de aplicaciones.
ms.openlocfilehash: 270315e15a79b97b55aa729d4b7e9b39930ee82c
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58571150"
---
# <a name="manage-app-policies"></a>Administrar directivas de aplicación

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Para mantenerse al día con las aplicaciones más recientes que usa su organización, responder a nuevos ataques basados en aplicaciones y gestionar los cambios continuos en las necesidades de cumplimiento de las aplicaciones, es posible que deba administrar las directivas de aplicación mediante estas acciones:

- Crear nuevas directivas destinadas a nuevas aplicaciones
- Cambiar el estado de una directiva existente (activo, inactivo, modo de auditoría)
- Cambiar las condiciones de una directiva existente
- Cambiar las acciones de una directiva existente para la corrección automática de alertas

Este es un ejemplo de un proceso para administrar una directiva existente:

1. Edite la directiva:

  - Cambie la configuración de la directiva.
  - Si es necesario, cambie el estado a **modo de auditoría** para las pruebas.

2. Compruebe el comportamiento esperado, como las alertas generadas.
1. Si el comportamiento no es el esperado, vuelva al paso 1.
1. Si el comportamiento es el esperado, edite la directiva y cambie su estado a activo (si es necesario).

![Flujo de trabajo de administración de directivas de aplicaciones.](../media/manage-app-protection-governance/mapg-manage-policy-process.png)

## <a name="editing-an-app-policy-configuration"></a>Editar la configuración de una directiva de aplicación

Para cambiar la configuración de una directiva de aplicación existente:

- Seleccione la directiva en la lista de directivas y, a continuación, seleccione **Editar** en el panel de directivas de aplicación.
- Seleccione los puntos suspensivos verticales de la directiva en la lista y, a continuación, seleccione **Editar**.

Para la página **Editar directiva**, recorra las páginas y realice los cambios adecuados:

- **Descripción**: cambie la descripción para que sea más fácil comprender el propósito de la directiva.
- **Gravedad**
- **Configuración de directiva**: cambie el conjunto de aplicaciones a las que se aplica la directiva. También puede optar por usar las condiciones existentes o modificarlas.
- **Acciones**: cambie la acción de corrección automática para las alertas generadas por la directiva.
- **Estado**: cambie el estado de la directiva.

## <a name="deleting-an-app-policy"></a>Eliminación de una directiva de aplicación

Para eliminar una directiva de aplicación:

- Seleccione la directiva en la lista de directivas y, a continuación, seleccione **Eliminar** en el panel de directivas de aplicación.
- Seleccione los puntos suspensivos verticales de la directiva en la lista y, a continuación, seleccione **Eliminar**.

Una alternativa a la eliminación de una directiva de aplicación es cambiar su estado a inactivo. Una vez inactiva, no generará alertas. Por ejemplo, en lugar de eliminar una directiva de aplicación para una aplicación con un conjunto específico de condiciones que pueden ser útiles para una directiva futura, cambie el nombre de la directiva de aplicación para indicar su utilidad y establezca su estado en inactivo. Más adelante, podrá volver a la directiva, modificarla para una aplicación similar y establecer su estado en modo de auditoría o inactivo.
