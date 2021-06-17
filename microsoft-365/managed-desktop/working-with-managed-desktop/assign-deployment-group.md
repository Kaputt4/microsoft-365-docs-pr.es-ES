---
title: Asignar dispositivos a un grupo de implementación
description: Cómo especificar el grupo de implementación en el que desea que los dispositivos se
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 19465d2d2f077859490c106b9c01f08beb6e3906
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985641"
---
# <a name="assign-devices-to-a-deployment-group"></a>Asignar dispositivos a un grupo de implementación

Escritorio administrado de Microsoft asignará dispositivos a los distintos grupos de implementación, pero puedes especificar o cambiar el grupo que un dispositivo se asigna a un dispositivo mediante el portal de administración. Cambias la asignación después de registrar un dispositivo o después de que un usuario se haya inscrito.

> [!IMPORTANT]
> Si cambias la asignación, las directivas específicas de ese grupo se aplicarán al dispositivo. El cambio puede instalar la versión más reciente de Windows 10 (incluidas las nuevas características o actualizaciones de calidad). Es mejor mover solo unos pocos dispositivos al principio y, a continuación, comprobar la experiencia de usuario resultante. Ten en cuenta que determinadas actualizaciones reiniciarán el dispositivo. Comprueba que has seleccionado los dispositivos adecuados para asignar. La asignación puede tardar hasta 24 horas en tener efecto.

Para asignar dispositivos a un grupo de implementación, siga estos pasos. Si quieres mover dispositivos separados a diferentes grupos, repite estos pasos para cada grupo.

1. En Microsoft Endpoint Manager, seleccione **Dispositivos** en el panel izquierdo. En la **Escritorio administrado de Microsoft,** seleccione **Dispositivos**.
2. Selecciona los dispositivos que quieras asignar. Todos los dispositivos seleccionados se asignarán al grupo que especifiques.
3. Selecciona **Acciones de dispositivo** en el menú.
4. Selecciona **Asignar dispositivo al grupo**. Se abre un fly-in.
5. Usa el menú desplegable para seleccionar el grupo al que mover los dispositivos y, a continuación, selecciona **Guardar**. El **grupo asignado por** cambiará a **Pendiente**.

Una vez completada la asignación, **Grupo** asignado por cambiará a **Administrador**  (indicado que realizó el cambio) y la columna Grupo mostrará la nueva asignación de grupo.

> [!NOTE]
> No puedes mover dispositivos a otros grupos si están en el estado de registro "error" o "pendiente".
>
>Si un dispositivo no se ha quitado correctamente, podría mostrar un estado de "listo". Si mueves un dispositivo de este tipo, es posible que el movimiento no se complete. Si no ves  Grupo asignado por cambio a **Pendiente** en el paso 5, comprueba que el dispositivo está disponible buscándolo en Intune. Para más información, consulte [Ver detalles de dispositivos de Intune](/mem/intune/remote-actions/device-inventory).