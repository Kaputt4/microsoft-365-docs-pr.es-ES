---
title: Notas de la versión de Microsoft Compliance Manager
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
description: El administrador de cumplimiento de Microsoft es una herramienta gratuita de evaluación de riesgos basada en flujos de trabajo en el portal de confianza de servicios de Microsoft. El administrador de cumplimiento le permite realizar un seguimiento, asignar y comprobar actividades de cumplimiento normativo relacionadas con los servicios en la nube de Microsoft.
ms.openlocfilehash: 3e710f83bebd94719ef66cde7844f1301611adf4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637540"
---
# <a name="microsoft-compliance-manager-preview-release-notes"></a>Notas de la versión de Microsoft Compliance Manager (versión preliminar)

La versión preliminar pública del administrador de cumplimiento le proporciona acceso anticipado a las actualizaciones y funciones futuras. Esta página contiene actualizaciones sobre características nuevas, funciones mejoradas y problemas conocidos con la versión actual.

Puede usar la herramienta del [Administrador de cumplimiento](https://servicetrust.microsoft.com/ComplianceManager) en el portal de confianza de [servicios](https://servicetrust.microsoft.com) para realizar un seguimiento, asignar y comprobar las actividades de cumplimiento normativo relacionadas con los servicios en la nube de Microsoft.

## <a name="improved-template-creation-and-update-process"></a>Proceso de actualización y creación de plantillas mejorados

Hemos actualizado el proceso de importación, exportación y modificación de plantillas para evaluaciones. La nueva experiencia simplificada le facilitará la tarea de llevar sus propias evaluaciones a su flujo de trabajo y mantenerlos actualizados.

### <a name="the-old-process"></a>El proceso antiguo

Hay dos formas de crear una plantilla en el administrador de cumplimiento. Puede copiar una plantilla existente o importar datos de plantilla de una hoja de cálculo de Excel a una plantilla nueva. En la página **plantillas** , debe seleccionar **+ Agregar plantilla** para crear una plantilla completamente nueva escribiendo un nombre, seleccionando dimensiones y cargando un archivo de Excel con un formato y un esquema específicos. O bien, puede activar la casilla **Copiar desde una plantilla existente** , seleccionar una plantilla para copiar y comprobar las dimensiones. Personalización de diseño la plantilla requería un proceso de varios pasos que comenzó seleccionando **Agregar control personalizado** después de crear la plantilla.

### <a name="the-new-process"></a>El nuevo proceso

Le hemos facilitado la creación de plantillas nuevas. En un proceso de **extensión** de un solo paso, puede Agregar una hoja de cálculo con sus acciones y controles a una plantilla de Microsoft existente para crear su propia versión personalizada. En la página **plantillas** del administrador de cumplimiento, seleccione **+ Agregar plantilla**. En el panel flotante de **plantilla** , seleccione la casilla **crear extensión a partir de plantilla global** . Puede Agregar personalizaciones con un nuevo formato de Excel que sea menos complejo que el anterior. Este nuevo proceso reemplaza la **copia anterior de una plantilla existente** y **agrega funciones de control personalizadas** .

Cada vez que se actualiza la evaluación original mediante el proceso de control de versiones que se describe a continuación, la evaluación personalizada heredará esas actualizaciones y conservará los controles personalizados.

También es más fácil modificar sus propias plantillas existentes. Puede exportar la plantilla, realizar cambios en el mismo libro y, a continuación, importarla con las modificaciones guardadas.

Vea las instrucciones detalladas sobre [Cómo crear plantillas](working-with-compliance-manager.md#templates) con este nuevo proceso.

## <a name="versioning-notice-and-control"></a>Aviso y control de versiones

Su organización recibió evaluaciones actualizadas en la versión de abril de 2020 del administrador de cumplimiento para ayudarle a alinearse con las actualizaciones de la regla y la certificación. Al avanzar, le proporcionaremos una forma clara de comprender y aceptar todas las actualizaciones futuras a través de las **alertas de control de versiones**.

Siempre que haya una actualización disponible para una plantilla de evaluación o una acción de mejora, un icono de alerta le indicará que hay una actualización lista. Al hacer clic en este icono, una ventana emergente explica la actualización y se le pide que acepte. Al seleccionar el icono de alerta, se revela un panel de control flotante en el que se explica la actualización y se le pide que la acepte. Obtenga más información sobre cómo [aceptar actualizaciones para las evaluaciones](working-with-compliance-manager.md#versioning-alerts-for-assessment-updates).

## <a name="common-actions-will-synch-status-across-groups"></a>Las acciones comunes sincronizarán el estado entre grupos

Si su organización tiene varios grupos de evaluaciones, el comportamiento de las acciones **técnicas** (es decir, las acciones que afectan a toda la organización) ha cambiado. Todas las acciones duplicadas entre grupos se han combinado en una sola acción. Esa única acción contiene todas las notas y evidencias cargadas de las versiones duplicadas. Con este cambio, las acciones técnicas se comportarán como lo hacían cuando pertenecían al mismo grupo. Cualquier cambio realizado en la acción en un grupo o evaluación se reflejará ahora en todas las instancias. El **Estado de implementación**, la **fecha de implementación**, el estado de **prueba**y la **fecha de prueba** reflejarán las actualizaciones más recientes.

## <a name="language-support"></a>Compatibilidad con idiomas

El administrador de cumplimiento ahora está disponible en los siguientes idiomas, además de en Inglés: Chino (simplificado), Chino (tradicional), Francés, alemán, Italiano, Japonés, Coreano, Portugués (Brasil), Ruso y español.

## <a name="known-issues-in-compliance-manager-preview"></a>Problemas conocidos en el administrador de cumplimiento (versión preliminar)

En la siguiente sección se tratan los problemas conocidos en la versión actual del administrador de cumplimiento.

### <a name="compliance-score"></a>Puntuación de cumplimiento 

- Para los elementos de acción marcados como **no en el ámbito**, la puntuación asignada al elemento de acción no se excluye del cálculo de la puntuación de cumplimiento. Los elementos de acción marcados **sin ámbito** no aumentan la puntuación de cumplimiento.

### <a name="secure-score"></a>Puntuación de seguridad

- Los resultados de puntuación seguros no están disponibles para algunos elementos de acciones en determinadas suscripciones de Microsoft 365 y Office 365. **No se pudo detectar** el resultado de la puntuación segura en estos casos.
- A veces, se devuelven resultados de puntuación seguros para las directivas y los elementos de acción correspondientes no completados.
- Para los nuevos inquilinos, se activan automáticamente las actualizaciones de puntuación seguras para todas las acciones. El administrador global puede establecer el cambio de actualización continua de puntuación segura en desactivado, lo que desactiva las actualizaciones para todas las acciones.
  - **Nota**: cuando las organizaciones implementan por primera vez Microsoft 365 u Office 365, la puntuación segura tardará aproximadamente siete días en completarse para recopilar los datos y factorizarlos en su puntuación. Durante este tiempo, la configuración de la opción de actualización continua de puntuación segura como **desactivada** y la configuración manual de una acción para **implementada** contará esa acción hacia su puntuación. Después de los siete días iniciales, al desactivar la actualización continua de la actualización segura, se habilitará la supervisión continua a partir de ese momento.
- Cuando las actualizaciones de calificaciones seguras están activadas, las acciones se supervisan activamente mediante una puntuación segura, aunque la fecha de prueba de la acción no se actualizará para reflejar la supervisión.
- Cuando se crean nuevas evaluaciones, las puntuaciones incluyen automáticamente los resultados de los controles administrados por Microsoft y la integración de la puntuación segura.
- Las acciones que no son compatibles con la integración de la puntuación segura se pueden implementar de forma manual. Una implementación manual se aplicará a la puntuación del grupo de la acción.

### <a name="export"></a>Export

- Se produce un error en la exportación de plantillas a JSON cuando el estado de la plantilla está establecido en **importado** o **pendiente de aprobación**.

### <a name="supported-browsers"></a>Exploradores compatibles

- Se admiten las versiones más recientes de Microsoft Edge, Chrome y Safari.
- Puede haber casos en los que los datos actualizados no aparezcan hasta que se actualice el explorador.
- La versión preliminar de Microsoft Edge no es compatible, pero no tiene problemas conocidos.
- Internet Explorer no es compatible.

### <a name="session-timeout"></a>Tiempo de espera de sesión

- Cuando se agota el tiempo de espera de una sesión, puede aparecer un error "se ha producido un problema". Para solucionarlo, vaya al [Administrador de cumplimiento](https://servicetrust.microsoft.com/ComplianceManager) e inicie sesión de nuevo.
