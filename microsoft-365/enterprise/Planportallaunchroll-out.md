---
title: Planeamiento del plan de lanzamiento del portal en SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: En este artículo se describe cómo puede planear el inicio del portal en SharePoint Online y qué pasos debe seguir para un inicio correcto.
ms.openlocfilehash: f04738900a25a2e74e24d6bf0f05b5bd6c7865f4
ms.sourcegitcommit: 6a981ca15bac84adbbed67341c89235029aad476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2022
ms.locfileid: "65753934"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>Planeamiento del plan de lanzamiento del portal en SharePoint Online

Un portal es un sitio SharePoint en la intranet con muchos visores de sitios que consumen contenido en el sitio. Las organizaciones grandes podrían tener varios portales. Por ejemplo, un portal de empresa y un portal de RR. HH. Por lo general, los portales tienen relativamente pocas personas que aportan y crean el sitio y su contenido. La mayoría de los visitantes del portal únicamente leen y usan el contenido.

En este artículo se describe cómo planear la implementación y el plan de implementación para SharePoint Online. También proporciona enfoques a seguir, ya que las pruebas de carga tradicionales no se permiten en SharePoint Online. SharePoint Online es un servicio en la nube y Microsoft administra las funcionalidades de carga, el estado y el equilibrio general de carga en el servicio.

Para ayudar a crear un portal correcto, siga los principios básicos, las prácticas y las recomendaciones que se detallan en [Creación, inicio y mantenimiento de un portal correcto](/sharepoint/portal-health).

El enfoque de implementación se resalta a continuación.

## <a name="portal-launch-scheduler"></a>Programador de inicio del portal

Use el programador de inicio del portal para liberar el portal a los usuarios de la organización en fases programadas. Más información:

![Icono de calendario.](../media/calendar.png) [Programador de inicio del portal](/microsoft-365/enterprise/portallaunchscheduler)

## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>Introducción al planeamiento de capacidad en SharePoint Online

Con el fin de usar eficazmente la capacidad y hacer frente a un crecimiento inesperado, en cualquier granja de servidores, tenemos automatización que realiza un seguimiento de determinados escenarios de uso. Aunque el crecimiento exacto es imprevisible para cualquier inquilino de una granja de servidores, la suma agregada de solicitudes es predecible con el tiempo. Al identificar las tendencias de crecimiento en SharePoint Online, podemos planear una expansión futura. Para obtener más información sobre [el planeamiento de capacidad y las pruebas de carga SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md).

Una parte clave de un lanzamiento correcto es el enfoque "wave" o "phased roll-out" que se detalla a continuación.

## <a name="can-i-load-test-sharepoint-online"></a>¿Puedo cargar la prueba SharePoint Online?

SharePoint Online es un entorno multiinquilino compartido que se equilibra entre granjas de servidores y la escala se ajusta de forma continua. Pruebas de carga de un entorno, como SharePoint Online, cuyos cambios de escala continuamente no solo le proporcionarán resultados inesperados, sino que no se permiten.

Más información: [Planeamiento de capacidad y pruebas de carga SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>Optimización de páginas siguiendo las directrices recomendadas

Las páginas de una implementación local no deben moverse simplemente como están en SharePoint Online sin revisarlas en función de las directrices recomendadas para SharePoint Online. El mejor enfoque es optimizar siempre cualquier página principal para cualquier sitio o portal de SharePoint, ya que aquí es donde la mayoría de los usuarios de la organización accederán como punto de partida para los sitios.

Se deben tener en cuenta algunos factores básicos:

- Las implementaciones locales pueden usar cachés tradicionales del lado servidor, como la caché de objetos, la caché de salida y la caché de blobs. Con las diferencias de topología en la nube, estas opciones no están necesariamente disponibles, ya que las diferencias de escala hacen que sean enfoques menos viables.
- Las páginas, características o personalizaciones usadas para el consumo en la nube deben optimizarse para una mayor latencia y las ubicaciones distribuidas de los usuarios, de modo que los usuarios de diferentes áreas o regiones tengan una experiencia más coherente. La nube ofrece optimizaciones como Content Delivery Networks (CDN) para optimizar una base de usuarios distribuida y para los SharePoint modernos, los últimos elementos web conocidos buenos (LKG) son utilizados por nuestros elementos web de fábrica (OOTB).

**Qué hacer**:

- Para todas las páginas de sitio de SharePoint Online, use la [herramienta Diagnóstico](./page-diagnostics-for-spo.md) de páginas, que es una extensión de Chromium que ayuda a analizar y proporcionar instrucciones. Esto lo pueden usar propietarios de sitios, editores, administradores y desarrolladores, ya que está diseñado para ser un punto de partida para el análisis y la optimización.
- Los desarrolladores también deben usar herramientas de desarrollo como F12 browser developer tool y CTRL-F12 en el explorador en páginas modernas. [Fiddler](https://www.telerik.com/download/fiddler) también se puede usar para revisar el peso del tamaño (el tamaño de la página en megabytes) de la página y el número de llamadas y elementos que afectan a la carga general de la página.

Esta sección fue un breve resumen para optimizar las páginas.  Para obtener más información, consulte:  [Creación, inicio y mantenimiento de un portal correcto](/sharepoint/portal-health).

## <a name="follow-a-wave--phased-roll-out-approach"></a>Seguir un enfoque de lanzamiento por fases o ola

El enfoque tradicional de big bang para los inicios de sitio no permitirá comprobar que las personalizaciones, orígenes externos, servicios o procesos se hayan probado a la escala correcta. Este enfoque no significa que se tardarán meses en iniciarse, pero se recomienda durante al menos varios días dependiendo del tamaño de la organización. Por lo tanto, después de un plan de implementación de oleadas se ofrece la opción de pausar y resolver problemas antes de continuar con la siguiente fase y, por lo tanto, reduce el número potencial de usuarios afectados por cualquier problema. SharePoint como servicio escala su capacidad en función del uso y el uso previsto y, aunque no necesitamos que nos notifique de su lanzamiento, debe seguir las directrices para garantizar el éxito.

Como se muestra en la siguiente imagen, a menudo el número de usuarios invitados es significativamente mayor que los que realmente usan el sitio. Esta imagen muestra una estrategia sobre cómo implementar una versión. Este método ayuda a identificar formas de mejorar el sitio SharePoint antes de que la mayoría de los usuarios lo vean.

![Graph mostrar usuarios invitados y activos.](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)

En la fase piloto, es bueno obtener comentarios de los usuarios en los que la organización confía y sabe que se va a comprometer. De este modo, es posible medir cómo se usa el sistema y cómo funciona.

Durante cada una de las oleadas, recopile los comentarios de los usuarios en torno a las características y el rendimiento durante cada oleada de implementación. La recopilación de comentarios tiene la ventaja de introducir lentamente el sistema y realizar mejoras a medida que el sistema se usa más. Esto también nos permite reaccionar ante el aumento de la carga, ya que el sitio se implementa para más usuarios y combinado con seguir las directrices para la optimización de páginas garantiza una experiencia positiva para los usuarios.

**Qué hacer**:

- Decida el tiempo de cada fase y asegúrese de que tiene una oportunidad de contingencia o pausa, en caso de que tenga que realizar ajustes antes de continuar
- Planee el primer grupo de usuarios que desea habilitar para asegurarse de que recibe los comentarios que necesita para avanzar.  Siempre que sea posible, seleccione un grupo activo de usuarios que proporcionará comentarios de forma oportuna.
- A medida que planee cada oleada, intente empezar con una base de usuarios pequeña (menos de 5000 usuarios). Aumente los tamaños de grupo a medida que continúe con cada ola. Al crear un enfoque escalonado, permite que las oportunidades de pausa sean más fáciles según sea necesario.
