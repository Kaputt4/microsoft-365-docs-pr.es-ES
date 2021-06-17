---
title: Grupos de implementación de dispositivos
description: Los grupos de implementación usados para administrar actualizaciones y otros cambios
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2d1f2325937488b95c40600f277835cca1329d1e
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985653"
---
# <a name="device-deployment-groups"></a>Grupos de implementación de dispositivos

Escritorio administrado de Microsoft los grupos de implementación para administrar la versión de las actualizaciones y los cambios de configuración en los dispositivos. Los dispositivos se agregan a grupos de implementación ("anillos" o "grupos de actualización") automáticamente cuando se inscriben en Escritorio administrado de Microsoft. Los grupos de implementación permiten que los dispositivos reciban cambios en una escala de tiempo por fases.

Es posible que quieras asignar determinados dispositivos solo con fines de prueba, o designar a usuarios anticipados específicos para recibir primero los cambios. Si tienes dispositivos críticos como los que usan los ejecutivos o que hacen funciones críticas para la empresa, es posible que quieras mantenerlos en el grupo que obtiene actualizaciones en la cadencia más lenta. Escritorio administrado de Microsoft permite especificar que un dispositivo debe permanecer en cualquiera de los siguientes grupos.

- **Prueba:** mejor para dispositivos que se usan para pruebas o usuarios que pueden tolerar cambios frecuentes y exposición a nuevas características y también proporcionar comentarios anticipados. Este grupo recibe cambios con frecuencia y las experiencias en este grupo tienen un efecto fuerte. El grupo De prueba está exento de los acuerdos de nivel de servicio establecidos y la compatibilidad con usuarios. Es mejor mover solo unos pocos dispositivos al principio y, a continuación, comprobar la experiencia del usuario. Escritorio administrado de Microsoft asignará automáticamente dispositivos a este grupo; solo tendrá dispositivos que especifiques.
- **En** primer lugar: ideal para usuarios de adopción temprana, validadores voluntarios o designados, profesionales de TI o representantes de funciones empresariales, es decir, personas que pueden validar los cambios y proporcionarle comentarios sobre la experiencia.
- **Broad** recibe los cambios en último lugar. La mayoría de la organización suele estar en este grupo. También puede especificar dispositivos que deben estar en este grupo y que solo deben recibir los cambios en último lugar porque están realizando funciones críticas empresariales o pertenecen a usuarios en roles críticos. 
- **Automático:** seleccione esta opción cuando desee Escritorio administrado de Microsoft asignar automáticamente dispositivos a uno de los otros grupos. (No asignaremos automáticamente dispositivos a Test). Si quieres liberar un dispositivo que hayas especificado anteriormente para que se pueda asignar automáticamente de nuevo, selecciona esta opción. 

Escritorio administrado de Microsoft algunos grupos adicionales para controlar las implementaciones, pero no podrás asignarles dispositivos. Sin embargo, puede mover dispositivos de esos grupos a uno de los grupos de este artículo. Para obtener más información sobre cómo Windows actualizaciones se administran en grupos, vea [How updates are handled in Escritorio administrado de Microsoft](updates.md).

Si un dispositivo está en un grupo especificado, El grupo **asignado por** dirá **Administrador**. Si Escritorio administrado de Microsoft ha asignado el grupo, dirá **Auto**. Mientras un dispositivo está en proceso de pasar a un grupo, dirá **Pendiente**. El **campo** Grupo siempre muestra el grupo en el que se encuentra actualmente el dispositivo y solo se actualiza cuando se completa un movimiento.

> [!IMPORTANT]
> No intente modificar directamente la pertenencia a estos grupos. Siga siempre los pasos descritos en [Asignar dispositivos a un grupo de implementación.](../working-with-managed-desktop/assign-deployment-group.md)
