---
title: Planeación del plan de implementación del inicio del portal en SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: En este artículo se describe cómo planear el inicio del portal en SharePoint Online y qué pasos seguir para un inicio correcto
ms.openlocfilehash: d77baac6209a4002bb1c27513d5ccfdf5c4ac28a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905697"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>Planeación del plan de implementación del inicio del portal en SharePoint Online

Un portal es un sitio de SharePoint en la intranet que tiene un gran número de visores de sitio que emplean el contenido en el sitio. En las organizaciones de gran tamaño podría haber varios de estos, por ejemplo, un portal de empresa y un portal de RRHH. Por lo general, los portales tienen relativamente pocas personas que aportan y crean el sitio y su contenido. La mayoría de los visitantes del portal únicamente leen y usan el contenido.

En este artículo se describe cómo planear el plan de implementación y lanzamiento en SharePoint Online. También proporciona métodos a seguir, ya que las pruebas de carga tradicionales no están permitidas en SharePoint Online. SharePoint Online es un servicio en la nube y Microsoft administra las capacidades de carga, el estado y el equilibrio general de carga del servicio.

Para ayudar a crear un portal correcto, siga los principios, prácticas y recomendaciones básicos que se detallan en [crear,](/sharepoint/portal-health) iniciar y mantener un portal en buen estado 

El enfoque de implementación se resalta a continuación.

## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>Información general sobre la planeación de capacidad en SharePoint Online
Para usar de forma eficiente la capacidad y hacer frente a un crecimiento inesperado, en cualquier granja de servidores, tenemos una automatización que realiza un seguimiento de determinados escenarios de uso. Aunque el crecimiento exacto es impredecible para cualquier inquilino de una granja de servidores, la suma agregada de solicitudes es predecible con el tiempo. Al identificar las tendencias de crecimiento en SharePoint Online, podemos planear la expansión futura. Para obtener más información sobre [la planeación de la capacidad y las pruebas de carga de SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md).

Una parte clave de un inicio correcto es el enfoque "wave" o "phased roll-out" que se detalla a continuación. 

## <a name="can-i-load-test-sharepoint-online"></a>¿Puedo cargar la prueba de SharePoint Online?
SharePoint Online es un entorno compartido de varios inquilinos que se equilibra entre granjas de servidores y la escala se ajusta de forma continua. Prueba de carga de un entorno, como SharePoint Online, cuya escala cambia continuamente no solo le dará resultados inesperados, sino que no está permitido. 

Más información:  [Planeación de capacidad y pruebas de carga de SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>Optimizar páginas siguiendo las directrices recomendadas
Las páginas de una implementación local no deben moverse simplemente como están en SharePoint Online sin revisarlas con las directrices recomendadas para SharePoint Online. El mejor enfoque es optimizar siempre cualquier página principal de cualquier sitio o portal de SharePoint, ya que aquí es donde la mayoría de los usuarios de la organización accederán como punto de partida para los sitios.

Se deben tener en cuenta algunos factores básicos:
- Las implementaciones locales pueden aprovechar cachés tradicionales del lado servidor como caché de objetos, caché de salida y caché de blobs. Con las diferencias de topología en la nube, estas opciones no están necesariamente disponibles, ya que las diferencias de escala hacen que sean menos viables.
- Las páginas, características o personalizaciones que se usan para el consumo en la nube deben optimizarse para una mayor latencia, así como para las ubicaciones distribuidas de los usuarios, de modo que los usuarios de distintas áreas o regiones tengan una experiencia más coherente. La nube ofrece optimizaciones como redes de entrega de contenido (CDN) para optimizar para una base de usuarios distribuida, así como para SharePoint moderno, el último bien conocido (LKG) lo usan nuestros elementos web de fuera de la caja (OOTB).

### <a name="what-to-do"></a>Qué hacer:
 - Para todas las páginas de sitio de SharePoint Online, use la herramienta Diagnóstico [de](./page-diagnostics-for-spo.md)página , que es una extensión Chromium que le ayudará a analizar y proporcionar instrucciones. Esto puede ser usado por propietarios de sitios, editores, administradores y desarrolladores, ya que está diseñado para ser un punto de partida para el análisis y la optimización.
 - Los desarrolladores también deben usar herramientas de desarrollo como F12 browser developer tool, así como CTRL-F12 en el explorador en páginas modernas. [Fiddler](https://www.telerik.com/download/fiddler) también se puede usar para revisar el peso del tamaño (el tamaño de la página en megabytes) de la página y el número de llamadas y elementos que afectan a la carga general de la página. 

Esta sección fue un breve resumen para optimizar páginas.  Para obtener más información, [vea: Crear, iniciar y mantener un portal en buen estado.](/sharepoint/portal-health)

## <a name="follow-a-wave--phased-roll-out-approach"></a>Seguir un enfoque de implementación de Wave /Phased
El enfoque tradicional de big bang para los inicios de sitios no permitirá comprobar que las personalizaciones, orígenes externos, servicios o procesos se hayan probado a la escala correcta. Esto no significa que tarde meses en iniciarse, pero se recomienda durante al menos varios días en función del tamaño de la organización. Por lo tanto, seguir un plan de implementación de oleadas le ofrece la opción de pausar y resolver problemas antes de continuar con la siguiente fase y, por lo tanto, reduce el número potencial de usuarios afectados por cualquier problema. SharePoint como servicio escala su capacidad en función del uso y el uso previsto y, aunque no necesitamos que nos notifique su inicio, debe seguir las directrices para garantizar el éxito.
  
Como se muestra en la siguiente imagen, a menudo el número de usuarios invitados es significativamente mayor que los que usan realmente el sitio. Esta imagen muestra una estrategia sobre cómo lanzar una versión. Este método ayuda a identificar formas de mejorar el sitio de SharePoint antes de que la mayoría de los usuarios lo vean.
  
![Gráfico que muestra los usuarios invitados y activos](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)
  
En la fase piloto, es bueno obtener comentarios de los usuarios en los que la organización confía y sabe que participarán. De esta forma, es posible medir cómo se usa el sistema, así como cómo se está realizando.
  
Durante cada una de las oleadas, recopila los comentarios de los usuarios sobre las características, así como el rendimiento durante cada oleada de implementación. Esto tiene la ventaja de introducir lentamente el sistema y realizar mejoras a medida que el sistema obtiene más uso. Esto también nos permite reaccionar ante el aumento de carga a medida que el sitio se implanta para cada vez más usuarios y combinado con seguir las directrices para la optimización de páginas garantiza una experiencia positiva para los usuarios.

### <a name="what-to-do"></a>Qué hacer:
- Decida el tiempo de cada fase y asegúrese de que tiene una oportunidad de contingencia o pausa, si necesita realizar ajustes antes de continuar
- Planee el primer grupo de usuarios que desea habilitar, para asegurarse de que recibe los comentarios que necesita para avanzar. Esto significa que, siempre que sea posible, seleccione un grupo activo de usuarios que proporcionará comentarios de forma oportuna
- A medida que planee cada oleada, intente comenzar con una base de usuarios pequeña (menos de 5000 usuarios) y, a continuación, aumente los tamaños de grupo a medida que avance con cada oleada. Esto ayuda a crear un enfoque escalonado y permite oportunidades de pausa más fáciles que pueden ser necesarias.