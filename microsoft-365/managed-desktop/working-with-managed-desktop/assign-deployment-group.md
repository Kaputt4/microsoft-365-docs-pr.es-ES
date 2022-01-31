---
title: Asignar dispositivos a un grupo de implementación
description: Cómo especificar el grupo de implementación en el que desea que los dispositivos se
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 6f3d2c79c23a37e1e1a965f9a3f416052a49fa76
ms.sourcegitcommit: af73b93a904ce8604be319e8dc7cadaf65d50534
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "62281428"
---
# <a name="assign-devices-to-a-deployment-group"></a>Asignar dispositivos a un grupo de implementación

Microsoft Managed Desktop asignará dispositivos a los distintos grupos de implementación. Puedes especificar o cambiar el grupo al que se asigna un dispositivo mediante el portal de administración. Cambias la asignación después de registrar un dispositivo o después de que un usuario se haya inscrito.

> [!IMPORTANT]
> Si cambias la asignación, las directivas específicas de ese grupo se aplicarán al dispositivo. El cambio puede instalar la versión más reciente de Windows 10 (incluidas las nuevas características o actualizaciones de calidad). Es mejor mover solo unos pocos dispositivos al principio y, a continuación, comprobar la experiencia de usuario resultante. Ten en cuenta que determinadas actualizaciones reiniciarán el dispositivo. Comprueba que has seleccionado los dispositivos adecuados para asignar. La asignación puede tardar hasta 24 horas en tener efecto.

**Para asignar dispositivos a un grupo de implementación:**

Si quieres mover dispositivos separados a diferentes grupos, repite estos pasos para cada grupo.

1. En Microsoft Endpoint Manager, seleccione **Dispositivos** en el panel izquierdo.
1. En la **sección Escritorio administrado de Microsoft** , seleccione **Dispositivos**.
1. Selecciona los dispositivos que quieras asignar. Todos los dispositivos seleccionados se asignarán al grupo que especifiques.
1. Selecciona **Acciones de dispositivo** en el menú.
1. Selecciona **Asignar dispositivo a grupo**. Se abre un fly-in.
1. Usa el menú desplegable para seleccionar el grupo al que mover los dispositivos y, a continuación, selecciona **Guardar**. El **grupo asignado por** columna cambiará a **Pendiente**.

Una vez completada la asignación **, El** grupo asignado por columna cambiará a **Administrador** (indicado que realizó el cambio) y la  columna Grupo mostrará la nueva asignación de grupo.

> [!NOTE]
> No puedes mover dispositivos a otros grupos si están en el estado de registro "error" o "pendiente".
>
>Si un dispositivo no se ha quitado correctamente, podría mostrar un estado de "listo". Si mueves un dispositivo de este tipo, es posible que el movimiento no se complete. Si no ves Grupo asignado  por cambio de columna a Pendiente  en el paso 5, comprueba que el dispositivo está disponible buscándolo en Intune. Para más información, consulte [Ver detalles de dispositivos de Intune](/mem/intune/remote-actions/device-inventory).
