---
title: Registro de auditoría de administración de riesgos internos
description: Más información sobre el registro de auditoría de administración de riesgos internos en Microsoft Purview
keywords: Microsoft 365, Microsoft Purview, riesgo interno, administración de riesgos, cumplimiento
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: a671e25dabf5dc9c526e6e3a931a71035b908cc3
ms.sourcegitcommit: 221212fff9737e0ea386755deb8fed62ae9c254b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66787834"
---
# <a name="insider-risk-management-audit-log"></a>Registro de auditoría de administración de riesgos internos

El registro de auditoría de administración de riesgos internos le permite mantenerse informado sobre las acciones que se realizaron en las características de administración de riesgos internos. Este registro permite una revisión independiente de las acciones realizadas por los usuarios asignados a uno o varios grupos de roles de administración de riesgos internos. El registro de auditoría de administración de riesgos internos se habilita automáticamente en su organización y no se puede deshabilitar.

![Registro de auditoría de administración de riesgos internos.](../media/insider-risk-audit-log.png)

El registro de auditoría se actualiza de forma automática e inmediata cada vez que se producen actividades detectadas y el registro conserva información sobre la actividad durante 180 días (aproximadamente seis meses). Después de 180 días, los datos de la actividad se eliminan permanentemente del registro.

Las áreas incluidas en la detección de actividad incluyen:

- Directivas
- Casos
- Alertas
- Configuración
- Usuarios
- Plantillas de aviso

Para ver y exportar datos desde el registro de auditoría, los usuarios deben estar asignados a los grupos de roles *Insider Risk Management* o *Insider Risk Management Auditors* . Para obtener más información sobre los grupos de roles de administración de riesgos internos, consulte [Introducción a la administración de riesgos internos Paso 1: Habilitar permisos](insider-risk-management-configure.md#step-1-required-enable-permissions-for-insider-risk-management).

> [!NOTE]
> El registro de auditoría de administración de riesgos internos no está asociado al registro de auditoría de Microsoft 365, son sistemas de auditoría independientes y capturan información sobre actividades independientes. Deshabilitar la auditoría de Microsoft 365 no afecta a la auditoría de actividad dentro de la administración de riesgos internos.

## <a name="view-activity-in-the-insider-risk-audit-log"></a>Visualización de la actividad en el registro de auditoría de riesgos internos

Para ver la actividad de características detectada para la administración de riesgos internos, vaya a y seleccione el vínculo **Registro de auditoría de riesgos** internos en el área superior derecha de cualquier pestaña de administración de riesgos internos. De forma predeterminada, verá la siguiente información para las actividades de administración de riesgos internos:

- **Actividad:** Descripción de la actividad realizada dentro de la solución de administración de riesgos internos por un usuario.
- **Categoría:** Área o elemento donde se realizó la actividad. Por ejemplo, verá *Directivas* como la categoría cuando se realizaron actividades de cambio de directiva.
- **Actividad realizada por:** Nombre de usuario del usuario que realizó la actividad.
- **Fecha:** Fecha y hora en que se realizó la actividad. La fecha y hora son la fecha y hora locales de su organización.

Para obtener más información sobre una actividad registrada, seleccione la actividad para mostrar el panel de detalles de la actividad. Este panel incluye información adicional sobre la actividad.

## <a name="columns-and-filtering"></a>Columnas y filtrado

Para facilitar a los auditores la revisión de la actividad registrada, el filtrado se admite en el **registro de auditoría de riesgos de Insider**. Para el filtrado básico, las columnas de cola están disponibles para agregarlas a la vista con el fin de proporcionar diferentes dinámicas en los archivos y mensajes. Puede filtrar las actividades por los campos **Categoría, Intervalo de fechas** y **Actividad realizada por** .

Para agregar o quitar encabezados de columna para la cola de actividad, use el control **Personalizar columnas** y seleccione en las opciones de columna. Estas columnas se asignan a condiciones comunes admitidas en el **registro de auditoría de riesgos de Insider** y se enumeran más adelante en este artículo.

## <a name="audit-log-export"></a>Exportación de registros de auditoría

Los usuarios asignados a los grupos de roles *Insider Risk Management* o *Insider Risk Management Auditors* pueden exportar toda la actividad del registro de auditoría a un archivo de .csv (valores separados por comas) seleccionando **Exportar** en la página **Registro de auditoría de riesgos** internos. En función de la actividad, es posible que algunos campos de una actividad no sean aplicables a la actividad y estos campos aparecerán en blanco en el archivo exportado.

El archivo contiene información de actividad para los campos siguientes:

- **Actividad realizada por:** Nombre de usuario del usuario que modifica un valor de elemento. Los usuarios enumerados aquí se asignaron a uno o varios de los siguientes grupos de roles de [administración de riesgos internos](insider-risk-management-configure.md#step-1-required-enable-permissions-for-insider-risk-management): *Insider Risk Management*, *Insider Risk Management Admins*, *Insider Risk Management Analysts*, *Insider Risk Management Investigators*. Cada grupo de roles tiene distintos niveles de permisos para administrar las características de riesgo internos.
- **Actividad:** Actividad realizada en un elemento. Los valores son *Viewed, Deleted, Added, Edit policy, Case, User, Alert* y *Settings.*
- **Agregado**: objetos que se agregaron durante la actividad, como usuarios, tipos de archivo o dominios.
- **Volumen de alertas**: el nivel de volumen de alertas definido en la configuración de administración de riesgos internos.
- **Importe**: importes del indicador personalizado seleccionados actualmente para una directiva.
- **Id. de** recurso: el identificador de recurso del recurso físico de prioridad en el que se realizó la actividad.
- **Categoría:** Categoría del elemento modificado. Los valores son *directivas, casos, usuarios, alertas, configuración* y *plantillas de aviso.*
- **Fecha:** Fecha y hora, que aparecen en la fecha y hora locales de la organización.
- **Descripción**: la entrada de descripción del usuario para el objeto en el que se actúa (por ejemplo, una directiva o un grupo de usuarios prioritarios).
- **Directiva DLP**: directiva de Prevención de pérdida de datos de Microsoft Purview (DLP) seleccionada para desencadenar la inclusión en una directiva de administración de riesgos internos.
- **Indicador**: indicador en la configuración de riesgo interno en la que se realizó la actividad (por ejemplo, agregar o quitar un indicador).
- **Plantilla de aviso**: plantilla de aviso en la que se realizó la actividad.
- **Número de días**: ventana de activación de directiva definida en la configuración de riesgo interno.
- **Número de archivos**: límite de volumen de archivos definido en la configuración de administración de riesgos internos.
- **Plantilla de** directiva: la plantilla de directiva en la que actuaron los indicadores pertenece a .
- **Importe anterior**: importes del indicador personalizado seleccionados anteriormente para una directiva.
- **Grupo de usuarios prioritarios**: grupo de usuarios de prioridad en el que se realizó la actividad.
- **Quitado**: objetos que se quitaron durante la actividad, como usuarios, tipos de archivo o dominios.
- **Remitente**: campo remitente de la plantilla de aviso en la que se realizó la actividad.
- **Directiva de destino**: la directiva en la que se realizó la actividad (por ejemplo, agregar un usuario a o quitar un usuario).
- **Cuerpo del mensaje de plantilla**: cuerpo del mensaje de la plantilla de aviso en la que se realizó la actividad.
- **Asunto de plantilla**: campo asunto de la plantilla de aviso en la que se realizó la actividad.
- **Usuario:** Usuario en el que se realizó la actividad.
