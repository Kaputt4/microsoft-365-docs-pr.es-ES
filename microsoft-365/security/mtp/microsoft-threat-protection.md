---
title: Microsoft 365 defender
description: Microsoft 365 defender es una solución coordinada de protección contra amenazas diseñada para proteger dispositivos, identidades, datos y aplicaciones
keywords: Introducción a la protección contra amenazas de Microsoft, seguridad de Cyber, amenazas persistentes avanzadas, seguridad empresarial, dispositivos, dispositivo, identidad, usuarios, datos, aplicaciones, incidentes, investigación automatizada y corrección, búsqueda avanzada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: a8d25ba0b36ad6ba1651ffe19e3e2f6e241548c7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843809"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 defender



Microsoft 365 defender es un conjunto de aplicaciones unificadas de defensa previa y posterior a la infracción de la empresa que coordinan de forma nativa la detección, prevención, investigación y respuesta en puntos de conexión, identidades, correo electrónico y aplicaciones para proporcionar protección integrada contra ataques sofisticados.

Con la solución integrada Microsoft 365 defender, los profesionales de seguridad pueden unir las señales de amenaza que reciben cada uno de estos productos y determinar el alcance completo y el impacto de la amenaza; Cómo entró en el entorno, qué se ve afectado y cómo afecta actualmente a la organización. Microsoft 365 defender realiza acciones automáticas para evitar o detener el ataque y Autocorregir los buzones de correo, los extremos y las identidades de usuario afectados.  


<center><h2>Servicios de Microsoft 365 defender</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft defender para extremo</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft defender para Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Microsoft defender para identidad</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>


>[!TIP]
>Consulte esta [Guía interactiva de Microsoft 365 defender](https://aka.ms/MTP-Interactive-Guide).


Microsoft 365 defender Suite protege: 
- **Extremos con Microsoft defender for Endpoint** -Microsoft defender for Endpoint es una plataforma de punto de conexión unificada para la protección preventiva, la detección tras infracción, la investigación automatizada y la respuesta. 
- El **correo electrónico y la colaboración con Microsoft defender para office 365** -defender para Office 365 protege a su organización frente a amenazas malintencionadas que plantean mensajes de correo electrónico, vínculos (URL) y herramientas de colaboración. 
- **Identidades con Microsoft defender para identidad y Azure ad Identity Protection** -Microsoft defender for Identity usa señales de Active Directory para identificar, detectar e investigar amenazas avanzadas, identidades en peligro y acciones indirectas dañinas dirigidas a la organización. 
- **Aplicaciones con Microsoft Cloud App Security** : Microsoft Cloud App Security es una solución completa de SaaS cruzadas que ofrece visibilidad profunda, controles de datos seguros y una mejor protección contra amenazas para las aplicaciones en la nube. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

La única capa de productos cruzados de Microsoft 365 defender aumenta los componentes individuales del conjunto de programas para:
- Ayudar a proteger contra ataques y coordinar respuestas defensivas en la serie a través del uso compartido de señales y acciones automatizadas
- Agregue un comentario a toda la historia del ataque a través de alertas de productos, comportamientos y contexto para los equipos de seguridad mediante la incorporación de datos sobre alertas, eventos sospechosos y activos afectados a ' incidentes '.
- Automatizar la respuesta a la intromisión mediante la activación de la autorreparación para los activos afectados mediante la corrección automatizada.
- Permitir que los equipos de seguridad realicen una búsqueda de amenazas detallada y eficaz en los datos de la oficina y el punto de conexión

![Imagen de la página información general sobre incidentes](../../media/overview-incident.png) <br>
Incidente entre productos (Introducción)

![Imagen de la cola de alertas](../../media/incident-list.png)<br>
Todas las alertas relacionadas en los productos de la Suite están relacionadas entre sí en un solo incidente (vista de alertas)

![Imagen de la cola de incidentes](../../media/advanced-hunting.png)<br>
Búsqueda basada en consultas sobre los datos de correo electrónico sin procesar de los extremos


Las características para varios productos de Microsoft 365 defender incluyen: 
- **Panel único de productos cruzados de Glass** -central permite ver toda la información sobre detecciones, activos afectados, acciones automatizadas tomadas y pruebas relacionadas en una única cola y un solo panel en [Security.Microsoft.com](https://security.microsoft.com). 
- **Cola de incidentes combinados** : para ayudar a los profesionales de la seguridad a centrarse en lo que es crítico garantizar que el ámbito del ataque completo, los activos afectados y las acciones de corrección automatizadas se agrupen y se exponen de manera oportuna. 
- **Respuesta automática a amenazas** : la información de amenazas críticas se comparte en tiempo real entre los productos de Microsoft 365 defender para ayudar a detener la progresión de un ataque. Por ejemplo, si se detecta un archivo malintencionado en un extremo protegido por Microsoft defender para el punto de conexión, se indicará a defender para Office 365 que debe examinar y quitar el archivo de todos los mensajes de correo electrónico. El paquete de seguridad completo de Microsoft 365 bloqueará el archivo a la vista.
- **Recuperación automática de dispositivos comprometedores, identidades de usuario y buzones de correo** -Microsoft 365 defender utiliza acciones y guías automáticas con tecnología de AI para volver a corregir los activos afectados a un estado seguro. Microsoft 365 defender aprovecha las capacidades de corrección automáticas de los productos de la Suite para garantizar que todos los activos afectados relacionados con un incidente se corrigen automáticamente siempre que sea posible.
- **Búsqueda de amenazas entre productos** : los equipos de seguridad pueden aprovechar su exclusivo conocimiento de la organización para buscar signos de peligro mediante la creación de sus propias consultas personalizadas sobre los datos sin procesar recopilados por los distintos productos de protección. Microsoft 365 defender proporciona acceso basado en consultas a 30 días de señales históricas sin procesar y datos de alerta a través de datos de extremos y de Microsoft defender para Office 365. 


## <a name="get-started"></a>Introducción
Se deben cumplir los requisitos de licencia de Microsoft 365 defender para poder habilitar el servicio en el centro de seguridad de Microsoft 365 en [Security.Microsoft.com](https://security.microsoft.com). Para obtener más información, lea:
- [Requisitos de licencia](prerequisites.md#licensing-requirements)
- [Activar Microsoft 365 defender](mtp-enable.md)
