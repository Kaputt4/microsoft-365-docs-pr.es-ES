---
title: Priorizar incidentes en Microsoft 365 Defender
description: Obtenga información sobre cómo filtrar incidentes de la cola de incidentes en Microsoft 365 Defender
keywords: incidente, cola, información general, dispositivos, identidades, usuarios, buzón, correo electrónico, incidentes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3b381749108d4a75024d9a546c0d3f1631c948ed
ms.sourcegitcommit: 76f3c75413cc960289489d0ca29efadb8a9a5b31
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "51887262"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Priorizar incidentes en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Microsoft 365 Defender aplica análisis de correlación y agrega alertas relacionadas e investigaciones automatizadas de diferentes productos en un incidente. Microsoft 365 Defender también desencadena alertas únicas en actividades que solo se pueden identificar como malintencionadas dada la visibilidad de extremo a extremo que Microsoft 365 Defender tiene en todo el conjunto de productos. Esta vista ofrece a los analistas de seguridad la historia de ataques más amplia, lo que les ayuda a comprender mejor y tratar las amenazas complejas en toda la organización.

La **cola Incidentes muestra** una colección de incidentes que se crearon en dispositivos, usuarios y buzones. Le ayuda a ordenar los incidentes para asignar prioridades y crear una decisión de respuesta de ciberseguridad fundamentada. 

You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Ejemplo de la cola de incidentes":::

De forma predeterminada, la cola de incidentes en el centro de seguridad de Microsoft 365 muestra incidentes vistos en los últimos seis meses. El incidente más reciente está en la parte superior de la lista para que pueda verlo primero.

La cola de incidentes tiene columnas personalizables (seleccione **Elegir** columnas) que le dan visibilidad de distintas características del incidente o de las entidades afectadas. Esto le ayuda a tomar una decisión fundamentada con respecto a la priorización de incidentes para su análisis.

Para obtener visibilidad adicional de un vistazo, la nomenclatura automática de incidentes genera nombres de incidentes basados en atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías. Esto le permite comprender rápidamente el ámbito del incidente.

Por ejemplo: *Incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*

> [!NOTE]
> Los incidentes que existían antes de la implementación de la nomenclatura automática de incidentes no tendrán su nombre cambiado.

La cola de incidentes también expone varias opciones de filtrado que, cuando se aplican, le permiten realizar un amplio barrido de todos los incidentes existentes en su entorno o decidir centrarse en un escenario o amenaza específicos. Aplicar filtros en la cola de incidentes puede ayudar a determinar qué incidente requiere atención inmediata. 

## <a name="available-filters"></a>Filtros disponibles

En la cola de incidentes  predeterminada, puede seleccionar Filtros para ver un panel Filtros, desde el que puede ver un conjunto filtrado de incidentes. Aquí le mostramos un ejemplo.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Ejemplo del panel de filtros de la cola de incidentes":::

En esta tabla se enumeran los nombres de filtro disponibles.

| Nombre del filtro | Descripción |
|:-------|:-----|
| Asignado a | Puede elegir mostrar las alertas que se le han asignado o las que controla la automatización. |
| Categorías | Elija categorías para centrarse en tácticas, técnicas o componentes de ataque específicos vistos. |
| Clasificación | Filtrar incidentes en función de las clasificaciones establecidas de las alertas relacionadas. Los valores incluyen alertas verdaderas, alertas falsas o no establecidas. |
| Confidencialidad de datos | Algunos ataques tienen por objetivo extraer datos confidenciales o importantes. Al aplicar un filtro para ver si hay datos confidenciales implicados en el incidente, puede determinar rápidamente si la información confidencial se ha visto comprometida y así dar prioridad a estos incidentes. <br><br> Solo se aplica si se ha activado Microsoft Information Protection. |
| Grupo de dispositivos | Filtrar por grupos de dispositivos definidos. |
| Estado de investigación | Filtrar incidentes por el estado de la investigación automatizada.  |
| Varias categorías | Puede elegir ver solo incidentes que se han asignado a varias categorías y, por lo tanto, puede causar más daños. |
| Múltiples orígenes del servicio  | Filtra para ver solo incidentes que contienen alertas de diferentes orígenes (Microsoft Defender para Endpoint, Microsoft Cloud App Security, Microsoft Defender para Identity, Microsoft Defender para Office 365). |
| Plataforma del sistema operativo | Limitar la vista de cola de incidentes por sistema operativo. |
| Orígenes del servicio | Al elegir un origen específico, puede concentrarse en los incidentes que contienen al menos una alerta del origen seleccionado. |
| Severity | La gravedad de un incidente indica el impacto que puede tener en los activos. Cuanto mayor sea la gravedad, mayor será el impacto y, por lo general, se requiere la atención más inmediata. |
| Estado | Puede limitar la lista de incidentes que se muestra en función de su estado para ver cuáles están activos o resueltos. |
|||

## <a name="incident-response-workflow"></a>Flujo de trabajo de respuesta a incidentes

Este es el flujo de trabajo típico para responder a incidentes:

1. Identifique y triage los incidentes de mayor prioridad para investigación y resolución.
2. Para cada incidente de prioridad alta, inicie una [investigación:](investigate-incidents.md)

   a. Vea el resumen del incidente para comprender su ámbito y gravedad y qué entidades se ven afectadas (la **pestaña Resumen).**

   b. Comience a ver las alertas para comprender su origen, ámbito y gravedad (la **pestaña** Alertas).

   c. Según sea necesario, recopila información sobre dispositivos, usuarios y buzones afectados (las pestañas **Dispositivos,** **Usuarios** y **Buzones).**

   d. Vea cómo Microsoft 365 Defender ha resuelto automáticamente algunas **alertas** (la pestaña Investigaciones).
   
   e. Según sea necesario, use la información del conjunto de datos para el incidente para obtener más información (la **pestaña Evidencia y** respuesta).

   A medida que investigue, debe preocuparse de:

   - Contención: reducir cualquier impacto adicional en el espacio empresarial.
   - Eliminación de la amenaza de seguridad.
   - Recuperación: restaurar los recursos del espacio empresarial en el estado en que se encontraban antes del incidente.

3. Después de resolver el incidente, tómese el tiempo para:

   - Comprender el tipo de ataque y su impacto.
   - Investigue el ataque en la comunidad de seguridad para obtener una tendencia de ataque de seguridad.
   - Recuerde el flujo de trabajo que usó para resolver el incidente y actualice los flujos de trabajo estándar y los libros de reproducción según sea necesario.
   - Determine si es necesario realizar cambios en la posición de seguridad y siga los pasos necesarios para implementarlos.

Este es un resumen del proceso básico.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-process.png" alt-text="Proceso básico para investigar incidentes":::

## <a name="next-step"></a>Paso siguiente

Después de determinar qué incidente requiere la prioridad más alta, selecciónelo e inicie la [investigación](investigate-incidents.md).

## <a name="see-also"></a>Vea también
- [Información general sobre incidentes](incidents-overview.md)
- [Investigar incidentes](investigate-incidents.md)
- [Administrar incidentes](manage-incidents.md)
