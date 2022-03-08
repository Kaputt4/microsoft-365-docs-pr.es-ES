---
title: Grupos de implementación de dispositivos
description: Los grupos de implementación usados para administrar actualizaciones y otros cambios
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 624bde84da9a0c35f5814e3b6c67c2d190683fc6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330305"
---
# <a name="device-deployment-groups"></a>Grupos de implementación de dispositivos

Microsoft Managed Desktop usa grupos de implementación para administrar la publicación de actualizaciones y cambios de configuración en los dispositivos. Los dispositivos se agregan a grupos de implementación ("anillos" o "grupos de actualización") automáticamente cuando se inscriben en el Escritorio administrado de Microsoft. Los grupos de implementación permiten que los dispositivos reciban cambios en una escala de tiempo por fases.

Es posible que quieras asignar determinados dispositivos solo con fines de prueba, o designar a usuarios anticipados específicos para recibir primero los cambios. Si tienes dispositivos críticos, como los que usan los ejecutivos o que hacen funciones críticas para la empresa, es posible que quieras mantenerlos en el grupo que obtiene actualizaciones en la cadencia más lenta. Microsoft Managed Desktop te permite especificar que un dispositivo debe permanecer en cualquiera de los siguientes grupos.

| Grupo | Descripción |
| ----- | ----- |
| Prueba | El grupo De prueba es el mejor para dispositivos que se usan para las pruebas o usuarios que pueden tolerar cambios frecuentes, exposición a nuevas características y pueden proporcionar comentarios anticipados.<br><br>Este grupo recibe cambios con frecuencia y las experiencias en este grupo tienen un efecto fuerte. El grupo De prueba está exento de los acuerdos de nivel de servicio establecidos y la compatibilidad con usuarios. Es mejor mover solo unos pocos dispositivos al principio y, a continuación, revisar la experiencia del usuario. Microsoft Managed Desktop no asignará automáticamente dispositivos a este grupo. Este grupo solo contendrá los dispositivos que especifique.
| Primero | El grupo First es ideal para adoptantes anticipados, voluntarios, validadores designados, profesionales de TI o representantes de funciones empresariales. Es decir, personas que pueden validar los cambios y proporcionarle comentarios sobre la experiencia.
| Rápida | El grupo Fast es ideal para representantes de funciones empresariales. Estas personas pueden validar los cambios antes de la implementación general.
| Amplias | El grupo Broad recibe los últimos cambios.<br><br>La mayoría de la organización suele estar en este grupo. Puede especificar dispositivos que deben estar en este grupo. Estos dispositivos deben recibir los cambios en último lugar porque están realizando funciones críticas empresariales o pertenecen a usuarios en roles críticos.
| Automático | Seleccione Automático cuando desee que Microsoft Managed Desktop asigne automáticamente dispositivos a uno de los otros grupos.<br><br>No asignaremos automáticamente dispositivos a Test. Si quieres liberar un dispositivo que hayas especificado anteriormente para que se pueda asignar automáticamente de nuevo, selecciona esta opción.

Para obtener más información sobre cómo Windows actualizaciones se administran en grupos, vea [How updates are handled in Microsoft Managed Desktop](updates.md).

## <a name="labels"></a>Etiquetas

El grupo asignado por columna contiene las siguientes etiquetas:

| Etiqueta | Descripción |
| ----- | ----- |
| Admin | El dispositivo está en un grupo especificado. |
| Automático | Microsoft Managed Desktop asignó el grupo. |
| Pending | El dispositivo está en proceso de pasar a un grupo. |

La **columna** Grupo siempre muestra el grupo en el que se encuentra actualmente el dispositivo y solo se actualiza cuando se completa un movimiento.

> [!IMPORTANT]
> No intente modificar directamente la pertenencia a estos grupos. Siga siempre los pasos descritos en [Asignar dispositivos a un grupo de implementación](../working-with-managed-desktop/assign-deployment-group.md).
