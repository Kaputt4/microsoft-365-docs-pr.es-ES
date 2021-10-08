---
title: Introducción a las directivas de aplicación
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: Introducción a las directivas de aplicación.
ms.openlocfilehash: c015a8ef97bc16963b670ae00c9067f35dafc1e0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60188402"
---
# <a name="get-started-with-app-policies"></a>Introducción a las directivas de aplicación

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Las directivas de aplicación para la gobernanza de aplicaciones de Microsoft le permiten implementar condiciones más proactivas o reactivas a fin de crear alertas o correcciones automáticas para las necesidades específicas de cumplimiento de aplicaciones en la organización.

Para ver una lista de las directivas de aplicaciones actuales, vaya al **Centro de cumplimiento de Microsoft 365 > Gobernanza de aplicaciones > Directivas**.

![La página de resumen de directivas de MAPG en el Centro de cumplimiento de Microsoft 365.](..\media\manage-app-protection-governance\mapg-cc-policies.png)

## <a name="whats-available-on-the-app-policies-dashboard"></a>Qué información está disponible en el panel de directivas de aplicaciones

Puede ver la cantidad de directivas activas, inactivas y de auditoría, así como la información relativa a cada directiva:

- **Nombre de la directiva**
- **Estado**

  - **Activa**: todas las acciones y evaluaciones de la directiva están activas.
  - **Inactive**: todas las acciones y evaluaciones de la directiva están deshabilitadas.
  - **Modo de auditoría**: la evaluación de directivas está activa (se desencadenarán alertas), pero las acciones de directiva están deshabilitadas.

- **Gravedad**: nivel de gravedad establecido en cualquier alerta activada debido a que esta directiva se evalúa como TRUE, lo que forma parte de la configuración de la directiva.
- **Número de alertas activas**: alertas generadas por la directiva, que tienen un estado **En curso** o **Nueva**.
- **Número total de alertas**: alertas tanto activas como resueltas para esta directiva.
- **Fecha de la última alerta**: fecha de la última alerta generada por esta directiva.
- **Última modificación**: fecha en que se cambió esta directiva por última vez.

De forma predeterminada, la lista de directivas se ordena por **Última modificación**. Para ordenar la lista según otro atributo, seleccione el nombre del atributo.

Al seleccionar una directiva, verá un panel de directivas detallado con esta información adicional:

- **Descripción**: una explicación más detallada del propósito de la directiva.
- **Creada por**: nombre principal de usuario (UPN) de la cuenta que creó la directiva.
- Lista del total de alertas y de las alertas activas generadas por esta directiva.

Puede editar o eliminar una directiva de aplicación seleccionando **Editar** o **Eliminar** en el panel de detalles de la directiva o seleccionando los puntos suspensivos verticales de la directiva en la lista de directivas.

También puede:

- Cree una nueva directiva. Puede comenzar con una directiva de uso de aplicaciones o una directiva de permisos.
- Exporte la lista de directivas a un archivo de valores separados por comas (CSV). Por ejemplo, podría abrir el archivo CVS en Microsoft Excel y ordenar la lista de directivas por **Gravedad** y, luego, por **Número total de alertas**.
- Busque en la lista de directivas.

## <a name="edit-an-existing-policy"></a>Editar una directiva existente

1. En el portal de gobernanza de aplicaciones, seleccione la pestaña **Directivas**.
1. Seleccione la directiva que desea editar. Se abrirá un panel en el lado derecho con los detalles de la directiva existente.
1. Seleccione **Editar**.
1. No puede cambiar el nombre de la directiva una vez creada, pero puede cambiar la descripción y la gravedad de la directiva. Seleccione **siguiente**.
1. Elija si desea continuar con la configuración de la directiva existente o personalizarla. Seleccione **No. Quiero personalizar la directiva** para realizar cambios. Seleccione **Siguiente**
1. Elija si esta directiva se aplicará a todas las aplicaciones o a las aplicaciones que especifique en la lista. Seleccione **Agregar aplicaciones** para agregar más aplicaciones a la lista si aplicas la directiva a aplicaciones específicas. Seleccione **Siguiente**
1. Elija si desea modificar las condiciones existentes de la directiva. Si decide modificar las condiciones, seleccione **Editar condiciones**. Seleccione **Siguiente**
1. Elija si desea deshabilitar la aplicación si desencadena las condiciones de la directiva. Seleccione **siguiente**.
1. Establezca el estado de la directiva en Auditoría, Activo o Inactivo. Seleccione **siguiente**.
1. Revise las opciones de configuración de la directiva y, si todo está como desea, seleccione **Enviar**.

## <a name="next-step"></a>Paso siguiente

[Cree una directiva de aplicación.](app-governance-app-policies-create.md)
