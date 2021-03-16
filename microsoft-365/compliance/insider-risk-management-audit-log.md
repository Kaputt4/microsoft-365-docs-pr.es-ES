---
title: Registro de auditoría de administración de riesgos de Insider
description: Obtenga información sobre el registro de auditoría de administración de riesgos de insider en Microsoft 365
keywords: Microsoft 365, administración de riesgos insider, administración de riesgos, cumplimiento
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: bda9633ab37fd21fd66b3a8a53d4dd522e48ced1
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "50820283"
---
# <a name="insider-risk-management-audit-log"></a>Registro de auditoría de administración de riesgos de Insider

El registro de auditoría de administración de riesgos insider le permite mantenerse informado sobre las acciones realizadas en las características de administración de riesgos internas. Este registro permite revisar de forma independiente las acciones realizadas por los usuarios asignados a uno o varios grupos de roles de administración de riesgos de información interna. El registro de auditoría de administración de riesgos interno se habilita automáticamente en la organización y no se puede deshabilitar.

![Registro de auditoría de administración de riesgos de Insider](../media/insider-risk-audit-log.png)

El registro de auditoría se actualiza automáticamente e inmediatamente siempre que se produzcan actividades supervisadas y el registro conserva información sobre la actividad durante 180 días (unos seis meses). Después de 180 días, los datos de la actividad se eliminan permanentemente del registro.

Entre las áreas incluidas en la supervisión de actividades se incluyen:

- Directivas
- Casos
- Alertas
- Configuraciones
- Usuarios
- Plantillas de aviso

Para ver y exportar datos desde el registro de auditoría, los usuarios deben estar asignados a los grupos de roles *Insider Risk Management* o *Insider Risk Management Auditors.* Para obtener más información acerca de los grupos de roles de administración de riesgos de insider, vea Introducción a la administración de riesgos [insider Step 1: Enabling permissions](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management).

>[!NOTE]
>El registro de auditoría de administración de riesgos interno no está asociado con el registro de auditoría de Microsoft 365, son sistemas de auditoría independientes y capturan información sobre actividades independientes. Deshabilitar la auditoría de Microsoft 365 no afecta a la auditoría de actividades dentro de la administración de riesgos de insider.

## <a name="view-activity-in-the-insider-risk-audit-log"></a>Ver actividad en el registro de auditoría de riesgos de insider

Para ver la actividad de características supervisada para la administración de riesgos de insider, vaya a y seleccione el vínculo Registro de auditoría de riesgos de Insider en el área superior derecha de cualquier pestaña de administración de riesgos de **insider.** De forma predeterminada, verá la siguiente información para las actividades de administración de riesgos de insider:

- **Actividad:** Una descripción de la actividad realizada en la solución de administración de riesgos insider por un usuario.
- **Categoría:** El área o elemento donde se realizó la actividad. Por ejemplo, verá Directivas *como* la categoría cuando se realizaron actividades de cambio de directiva.
- **Actividad realizada por:** Nombre de usuario del usuario que realizó la actividad.
- **Fecha:** La fecha y hora en que se realizó la actividad. La fecha y la hora son la fecha y hora locales de la organización.

Para obtener más información acerca de una actividad registrada, seleccione la actividad para mostrar el panel de detalles de la actividad. Este panel incluye información adicional sobre la actividad.

## <a name="columns-and-filtering"></a>Columnas y filtrado

Para facilitar que los auditores revisen la actividad registrada, se admite el filtrado en el registro de auditoría de riesgos **de Insider**. Para el filtrado básico, las columnas de cola están disponibles para agregar a la vista para proporcionar diferentes dinámicas en los archivos y mensajes. Puede filtrar las actividades por los campos **Categoría, Intervalo de fechas** y Actividad **que realizan.**

Para agregar o quitar encabezados de columna para la cola de actividades, use el **control** Personalizar columnas y seleccione en las opciones de columna. Estas columnas se asignan a condiciones comunes admitidas en el registro de auditoría de riesgos de **Insider** y se enumeran más adelante en este artículo.

## <a name="audit-log-export"></a>Exportación de registros de auditoría

Los usuarios asignados a los grupos de roles *Insider Risk Management* o *Insider Risk Management Auditors* pueden exportar toda la actividad del registro de auditoría a un archivo .csv (valores separados por comas) seleccionando **Exportar** en la página registro de auditoría de riesgos de **Insider.** Según la actividad, es posible que algunos campos de una actividad no sean aplicables a la actividad y estos campos aparecerán en blanco en el archivo exportado.

El archivo contiene información de actividad para los campos siguientes:

- **Actividad realizada por:** Nombre de usuario del usuario que modifica un valor de elemento. Los usuarios enumerados aquí se asignaron a uno o varios de los siguientes grupos de roles de administración de riesgos insider [:](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) *Insider Risk Management*, *Insider Risk Management Admins*, *Insider Risk Management Analysts*, *Insider Risk Management Investigators*. Cada grupo de roles tiene distintos niveles de permisos para administrar características de riesgo interno.
- **Actividad:** La actividad realizada en un elemento. Los valores *son Viewed, Deleted, Added, Edited policy, Case, User, Alert y* *Settings.*
- **Agregado:** objetos que se agregaron durante la actividad, como usuarios, tipos de archivo o dominios.
- **Volumen de alerta:** el nivel de volumen de alerta definido en la configuración de administración de riesgos de insider.
- **Importe:** importes del indicador personalizado seleccionados actualmente para una directiva.
- **Id. de** activo: el id. de activo del activo físico de prioridad en el que se realizó la actividad.
- **Categoría:** Categoría del elemento modificado. Los valores *son Directivas, Casos, Usuarios, Alertas, Configuración* y *Plantillas de aviso.*
- **Fecha:** Fecha y hora, enumerados en la fecha y hora local de la organización.
- **Descripción:** la descripción que el usuario ha especificado para el objeto en el que se actúa (como una directiva o un grupo de usuarios de prioridad).
- **Directiva DLP:** la directiva de prevención de pérdida de datos (DLP) seleccionada para desencadenar la inclusión en una directiva de administración de riesgos de información interna.
- **Indicador:** el indicador de la configuración de riesgo dentro de insider en la que se realizó la actividad (como agregar o quitar un indicador).
- **Plantilla de aviso:** plantilla de aviso en la que se realizó la actividad.
- **Número de días:** la ventana de activación de directivas definida en la configuración de riesgos de insider.
- **Número de archivos:** el límite de volumen de archivo definido en la configuración de administración de riesgos de insider.
- **Plantilla de directiva:** la plantilla de directiva a la que pertenecen los indicadores.
- **Importe anterior:** importes del indicador personalizado seleccionados anteriormente para una directiva.
- **Grupo de usuarios prioritario:** el grupo de usuarios de prioridad en el que se realizó la actividad.
- **Removed:** objetos que se quitaron durante la actividad, como usuarios, tipos de archivo o dominios.
- **Remitente:** el campo de remitente de la plantilla de aviso en la que se realizó la actividad.
- **Directiva de** destino: la directiva en la que se realizó la actividad (como agregar un usuario a o quitar un usuario de).
- **Cuerpo del mensaje de** plantilla: el cuerpo del mensaje de la plantilla de aviso en la que se realizó la actividad.
- **Asunto de plantilla:** el campo de asunto de la plantilla de aviso en la que se realizó la actividad.
- **Usuario:** Usuario en el que se realizó la actividad.
