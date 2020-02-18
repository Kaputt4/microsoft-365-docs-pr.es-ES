---
title: Resiliencia del Servicio de Microsoft 365
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Descripción del tema de la resiliencia
ms.openlocfilehash: 8cda7a861b6ea646ed9606674e26aaca551d1024
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597027"
---
# <a name="built-in-resiliency"></a>Resiliencia integrada

Como proveedor de colaboración en la nube, Microsoft reconoce la necesidad de ganar su confianza continuamente proporcionando soluciones que funcionen sistemáticamente y que gusten a los usuarios. Cuando un servicio determinado no está disponible, esto se denomina tiempo de inactividad (downtime). La definición de tiempo de inactividad varía en función de cada servicio de Microsoft 365, pero normalmente se refiere a un período de tiempo en el que los usuarios no pueden usar la funcionalidad esencial del servicio. Por ejemplo, la definición de tiempo de inactividad para SharePoint Online según el contrato de nivel de servicio de Microsoft 365 es esta:

**"Inactividad de SharePoint Online**: cualquier período de tiempo en el que los usuarios no puedan leer ni escribir ninguna parte de una colección de sitios de SharePoint Online para la que tengan los permisos adecuados".

Puede encontrar las definiciones de tiempo de inactividad para cada servicio en los [contratos de nivel de servicio](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37).

Para minimizar el tiempo de inactividad, tanto planeado como imprevisto, los servicios de Microsoft 365 están diseñados y se pueden gestionar para que estén altamente disponibles y sean resilientes frente a errores centrándose en cuatro áreas:

## <a name="activeactive-design"></a>Diseño activo/activo

En Microsoft 365 trabajamos para que todos los servicios estén diseñados y puedan funcionar con diseño activo/activo que aumenta la resiliencia. Esto significa que siempre hay varias instancias de un servicio en ejecución que pueden responder a las solicitudes de usuario y que se hospedan en centros de datos geográficamente alejados. Todo el tráfico de usuarios entra a través del servicio Front Door de Microsoft y se redirige automáticamente a una instancia localizada de forma óptima del servicio y evitando cualquier error de servicio para prevenir o reducir el impacto en nuestros clientes.

## <a name="reduce-incident-scope"></a>Reducir el ámbito de la incidencia

El ámbito de una incidencia de servicio se mide en función de su gravedad, el tiempo que dura y cuántos clientes se ven afectados. Nos esforzamos por limitar el alcance de cada incidencia:

- proporcionando varias instancias de cada servicio compartimentadas entre sí
- implementando actualizaciones de una forma controlada y graduada mediante anillos de validación, de modo que los problemas que puedan surgir de la actualización se puedan detectar y mitigar anticipadamente en el proceso de implementación. Esto permite la regresión de la actualización, si es necesario, y en primer lugar en un grupo reducido de Microsoft (anillo interno) antes de que se implemente en grupos de mayor tamaño, como en el caso de todos los 140.000 empleados de Microsoft (anillo 2) y, a continuación, en la adopción temprana de los anillos (anillo 3) y, finalmente, para todos los clientes globalmente (anillo 4).
- promoviendo las mejoras en la supervisión gracias a la automatización. Microsoft 365 es muy grande y el tiempo de actividad objetivo del SLA es elevado. Al principio de una incidencia del servicio, si los seres humanos tuvieran que intervenir en la detección y respuesta, no podríamos responder lo suficientemente rápido para cumplir los SLA. La automatización es la clave para que la detección y respuesta de una incidencia de servicio sea rápida y eficaz. Cuanto más pronto tengamos conocimiento de algo, más rápido se podrá solucionar.

Junto con las funcionalidades activo/activo integradas en la arquitectura de servicio de Microsoft 365, estos esfuerzos reducen la gravedad, la duración y el número de clientes afectados durante una incidencia del servicio.  

## <a name="fault-isolation"></a>Aislamiento de fallos

Al igual que los servicios se diseñan y funcionan de un modo activo/activo y se compartimentan entre sí para evitar que uno de los errores afecte a otro, la base del código del servicio se desarrolla mediante principios de compartimentación similares llamados aislamiento de fallos. Las medidas de aislamiento de fallos son protecciones incrementales que se llevan a cabo en la propia base del código. Estas medidas ayudan a evitar que un problema en un área afecte a otras áreas de operación.
Las medidas de aislamiento de fallos se aplican en varias fases del desarrollo y la entrega de un servicio, incluido el desarrollo de código, la implementación de servicios, el equilibrio de carga y la replicación de la base de datos.

El Ciclo de vida de desarrollo de seguridad de Microsoft (SDL) promueve la resiliencia y consta de un conjunto de prácticas que admiten requisitos de seguridad y cumplimiento. El SDL guía a nuestros desarrolladores para crear servicios resilientes, seguros y compatibles. Entre los elementos clave del SDL se incluyen las revisiones de código, el modelado de amenazas, las pruebas de penetración y los procesos normalizados de respuesta ante incidencias en la nube de Microsoft.

El uso de los servicios de M365 está muy interconectado, pero los sistemas y la tecnología que los conforman se diseñan de forma que se limita el impacto en otros servicios de una incidencia del servicio. Por ejemplo, un problema que afecte a Exchange Online no afectará a la funcionalidad principal de Teams o un problema con la funcionalidad de búsqueda de SharePoint Online no afectará a la capacidad de los usuarios para cargar o descargar archivos.

## <a name="continuous-service-improvement"></a>Mejora continua del servicio

Cuando se experimenta una incidencia, nos lo tomamos en serio. Después de todo, la arquitectura redundante de la nube y los estrictos procesos internos tienen como objetivo mantener la accesibilidad a nuestros servicios. Durante una incidencia, las herramientas de supervisión detectan rápidamente los servicios afectados y, si su espacio empresarial está afectado, se le notificará inmediatamente a través de varios canales. Simultáneamente, los ingenieros siguen procesos bien definidos para clasificar el problema y llevar a cabo los pasos necesarios para restaurar el funcionamiento normal lo más rápido posible. Una vez que el servicio funciona con normalidad de nuevo, realizamos un examen posterior de incidencias como parte del ciclo de mejora continua del servicio. Durante la revisión posterior de incidencias, identificamos las causas principales de la incidencia y lo que fue necesario para corregir los problemas. Luego, teniendo en cuenta lo aprendido de la situación, lo aplicamos al diseño y a las operaciones de la totalidad de nuestra serie de ofertas. De esta forma, se evita que la misma causa principal afecte a otros servicios y a los clientes adicionales.
