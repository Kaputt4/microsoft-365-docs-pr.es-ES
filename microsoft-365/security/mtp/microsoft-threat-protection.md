---
title: Microsoft 365 Defender
description: Microsoft 365 Defender es una solución coordinada de protección contra amenazas diseñada para proteger dispositivos, identidades, datos y aplicaciones
keywords: introducción a la Protección contra amenazas de Microsoft, seguridad cibernética, amenaza persistente avanzada, seguridad empresarial, dispositivos, dispositivo, identidad, usuarios, datos, aplicaciones, incidentes, investigación y corrección automatizada, búsqueda avanzada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: e80a3d094ac8f5724bbe7daf72a0ded7d30091ba
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930575"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

> ¿Desea experimentar Microsoft 365 Defender? Puede [evaluarlo en un entorno de laboratorio o](https://aka.ms/mtp-trial-lab) ejecutar el proyecto piloto en [producción.](https://aka.ms/m365d-pilotplaybook)
>

Microsoft 365 Defender es un conjunto unificado de defensa empresarial anterior y posterior a la infracción que coordina de forma nativa la detección, prevención, investigación y respuesta entre puntos de conexión, identidades, correo electrónico y aplicaciones para proporcionar protección integrada contra ataques sofisticados.

Con la solución integrada de Microsoft 365 Defender, los profesionales de seguridad pueden unir las señales de amenaza que cada uno de estos productos recibe y determinar el alcance completo y el impacto de la amenaza; cómo se introdujo en el entorno, qué se ve afectado y cómo afecta actualmente a la organización. Microsoft 365 Defender toma medidas automáticas para evitar o detener el ataque y sanar automáticamente los buzones de correo, los puntos de conexión y las identidades de usuario afectados.  


<center><h2>Servicios de Microsoft 365 Defender</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender para punto de conexión</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender para Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Microsoft Defender para identidad</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Guía interactiva de Microsoft 365 Defender

En esta guía interactiva, aprenderá a proteger su organización con Microsoft 365 Defender. Verá cómo Microsoft 365 Defender puede ayudarle a detectar riesgos de seguridad, investigar ataques a su organización y evitar actividades dañinas automáticamente.

> [!VIDEO https://aka.ms/M365Defender-InteractiveGuide]



El conjunto de aplicaciones de Microsoft 365 Defender protege: 
- **Endpoints with Microsoft Defender for Endpoint** - Microsoft Defender for Endpoint is a unified endpoint platform for preventative protection, post-breach detection, automated investigation, and response. 
- El correo electrónico y la colaboración con Microsoft Defender para **Office 365:** Defender para Office 365 protege su organización contra las amenazas malintencionadas que suponen los mensajes de correo electrónico, los vínculos (URL) y las herramientas de colaboración. 
- Identidades con Microsoft Defender para Identidad y **Azure AD Identity Protection:** Microsoft Defender para Identidad usa señales de Active Directory para identificar, detectar e investigar amenazas avanzadas, identidades comprometidas y acciones internas malintencionadas dirigidas a su organización. 
- **Aplicaciones con Microsoft Cloud App Security:** Microsoft Cloud App Security es una solución completa entre SaaS que ofrece visibilidad profunda, controles de datos sólidos y protección contra amenazas mejorada para las aplicaciones en la nube. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

La capa única entre productos de Microsoft 365 Defender aumenta los componentes individuales del conjunto de aplicaciones para:
- Ayudar a proteger contra ataques y coordinar las respuestas de defensa en todo el conjunto de aplicaciones a través del uso compartido de señales y acciones automatizadas
- Narra la historia completa del ataque a través de alertas de producto, comportamientos y contexto para los equipos de seguridad uniendo datos sobre alertas, eventos sospechosos y activos afectados a "incidentes"
- Automatizar la respuesta al peligro desencadenando la recuperación automática para los activos afectados a través de una corrección automatizada
- Permitir que los equipos de seguridad realicen búsquedas de amenazas detalladas y eficaces en los puntos de conexión y los datos de Office

![Imagen de la página de información general sobre incidentes](../../media/overview-incident.png) <br>
Incidente entre productos (información general)

![Imagen de la cola de alertas](../../media/incident-list.png)<br>
Todas las alertas relacionadas en los productos del conjunto de servicios se correlacionaron en un solo incidente (vista de alertas)

![Imagen de la cola de incidentes](../../media/advanced-hunting.png)<br>
Búsqueda basada en consulta sobre datos sin procesar de correo electrónico y punto de conexión


Las características entre productos de Microsoft 365 Defender incluyen: 
- **Panel único de** cristal entre productos: vea toda la información de detecciones, activos afectados, acciones automatizadas tomadas y pruebas relacionadas en una sola cola y un único panel en [security.microsoft.com](https://security.microsoft.com). 
- Cola de incidentes **combinados:** para ayudar a los profesionales de seguridad a centrarse en lo que es fundamental al garantizar el ámbito de ataque completo, los activos afectados y las acciones de corrección automatizadas se agrupan y se ponen en contacto de forma oportuna. 
- **Respuesta automática a las amenazas:** la información de amenazas críticas se comparte en tiempo real entre los productos de Microsoft 365 Defender para ayudar a detener la progresión de un ataque. Por ejemplo, si se detecta un archivo malintencionado en un extremo protegido por Microsoft Defender para Endpoint, indicará a Defender para Office 365 que analice y quite el archivo de todos los mensajes de correo electrónico. Todo el conjunto de seguridad de Microsoft 365 bloqueará el archivo a la vista.
- Recuperación automática para **dispositivos, identidades** de usuario y buzones en peligro: Microsoft 365 Defender usa acciones automáticas con tecnología de IA y guías de juegos para corregir los activos afectados de nuevo a un estado seguro. Microsoft 365 Defender aprovecha las capacidades de corrección automática de los productos del conjunto de aplicaciones para garantizar que todos los activos afectados relacionados con un incidente se corrigen automáticamente siempre que sea posible.
- **Búsqueda** de amenazas entre productos: los equipos de seguridad pueden aprovechar sus conocimientos organizativos únicos para buscar signos de peligro mediante la creación de sus propias consultas personalizadas sobre los datos sin procesar recopilados por los distintos productos de protección. Microsoft 365 Defender proporciona acceso basado en consultas a 30 días de señales históricas sin procesar y datos de alerta en el punto de conexión y Microsoft Defender para datos de Office 365. 


## <a name="get-started"></a>Introducción
Se deben cumplir los requisitos de licencia de Microsoft 365 Defender para poder habilitar el servicio en el Centro de seguridad de Microsoft 365 [en security.microsoft.com](https://security.microsoft.com). Para obtener más información, lea:
- [Requisitos de licencia](prerequisites.md#licensing-requirements)
- [Activar Microsoft 365 Defender](mtp-enable.md)
