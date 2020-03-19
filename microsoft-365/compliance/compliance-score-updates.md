---
title: Actualizaciones de puntuación de cumplimiento de Microsoft
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Detalles sobre futuras actualizaciones de la puntuación de cumplimiento de Microsoft (versión preliminar), una característica del centro de cumplimiento de M365 que ayuda a simplificar y automatizar las evaluaciones de riesgos.
ms.openlocfilehash: c46b70d0762a805e4ecfc83b70173c56d21a3933
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857779"
---
# <a name="microsoft-compliance-score-preview-updates"></a>Actualizaciones de la puntuación de cumplimiento de Microsoft (versión preliminar)

 En este artículo se proporcionan detalles sobre futuras actualizaciones de la [puntuación de cumplimiento de Microsoft](compliance-score.md) y el administrador de cumplimiento de [Microsoft](compliance-manager-overview.md). Obtenga más información sobre su [relación](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager).

## <a name="improved-template-creation-and-update-processes"></a>Procesos de actualización y creación de plantillas mejorados

Estamos simplificando el proceso de importación, exportación y modificación de plantillas para evaluaciones. La nueva experiencia le permitirá llevar a cabo sus propias evaluaciones en la puntuación de cumplimiento y mantenerla actualizada.

### <a name="the-current-process"></a>El proceso actual

Hay dos formas de crear una plantilla en el administrador de cumplimiento. Puede copiar una plantilla existente o importar datos de plantilla de una hoja de cálculo de Excel a una plantilla nueva. Desde la página de **plantillas** , seleccione **+ Agregar plantilla** para crear una plantilla completamente nueva escribiendo un nombre, seleccionando dimensiones y cargando un archivo de Excel con un formato y un esquema específicos. O bien, puede activar la casilla **Copiar desde una plantilla existente** , seleccionar una plantilla para copiar y comprobar las dimensiones, tal como se muestra en la imagen siguiente. La personalización de la plantilla requiere un [proceso de varios pasos](working-with-compliance-manager.md#templates) que comienza seleccionando **Agregar control personalizado** después de crear la plantilla.

![Puntuación de cumplimiento: panel](../media/compliance-score-template-update-old.png "Proceso de copia de plantilla actual")

### <a name="whats-changing"></a>Cambios

Estamos haciendo que sea más fácil crear plantillas nuevas. En un proceso de **extensión** de un solo paso, puede Agregar una hoja de cálculo con sus acciones y controles a una plantilla de Microsoft existente para crear su propia versión personalizada. En el panel flotante de **plantilla** , active la casilla **crear extensión a partir de plantilla global** , como se muestra en la imagen siguiente. A continuación, agregará las personalizaciones con un nuevo formato de Excel que es menos complejo que el actual. Este nuevo proceso reemplaza la **copia actual de una plantilla existente** y **agrega funciones de control personalizadas** .

Cada vez que se actualiza la evaluación original mediante el proceso de control de versiones que se describe a continuación, la evaluación personalizada heredará esas actualizaciones y conservará los controles personalizados.

También estamos haciendo que sea más fácil modificar sus propias plantillas existentes. Puede exportar la plantilla, realizar cambios en el mismo libro y, a continuación, importarla con las modificaciones guardadas.

![Puntuación de cumplimiento: panel](../media/compliance-score-template-update-new.png "Nuevo proceso de creación de plantillas")

## <a name="versioning-notice-and-control"></a>Aviso y control de versiones

Su organización recibirá evaluaciones actualizadas en la próxima versión de la puntuación de cumplimiento y el administrador de cumplimiento para ayudarle a alinearse con las actualizaciones de la regla y la certificación.

En el futuro, siempre que haya una actualización disponible para una plantilla de evaluación o una acción de mejora, un icono de alerta le indicará que hay una actualización lista. Al hacer clic en este icono, una ventana emergente explica la actualización y se le pide que acepte. A continuación se muestra un ejemplo de la alerta de control de versiones para una evaluación:

![Puntuación de cumplimiento: alerta de control de versiones](../media/compliance-score-assessment-version.png "Alerta de actualización de la versión de evaluación")

Al seleccionar el icono de alerta, se revela un panel de control flotante en el que se explica la actualización y se le pide que acepte:

![Puntuación de cumplimiento: control flotante de control de versiones](../media/compliance-score-assessment-version-accept.png "Panel de confirmación de actualización de evaluación")

## <a name="common-actions-will-synch-status-across-groups"></a>Las acciones comunes sincronizarán el estado entre grupos

Si su organización tiene varios grupos de evaluaciones, el comportamiento de las acciones **técnicas** (es decir, las acciones que afectan a toda la organización) cambiará. Todas las acciones duplicadas entre grupos se combinarán en una sola acción. Esa única acción contendrá todas las notas cargadas y la evidencia de las versiones duplicadas. Con este cambio, las acciones técnicas se comportarán tal como lo hacen actualmente cuando pertenezcan al mismo grupo. Cualquier cambio realizado en la acción en un grupo o evaluación se reflejará ahora en todas las instancias. El **Estado de implementación**, los **DAT de implementación**, el estado de **prueba**y la **fecha** de prueba reflejarán las actualizaciones más recientes.

## <a name="language-support"></a>Compatibilidad con idiomas

La puntuación de cumplimiento ahora estará disponible en los siguientes idiomas, además de en Inglés: Chino (simplificado), Chino (tradicional), Francés, alemán, Italiano, Japonés, Coreano, Portugués (Brasil), Ruso y español.
