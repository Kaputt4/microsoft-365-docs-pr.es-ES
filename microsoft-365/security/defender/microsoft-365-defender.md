---
title: Microsoft 365 Defender
description: Microsoft 365 Defender es una solución de protección contra amenazas coordinada diseñada para proteger dispositivos, identidad, datos y aplicaciones
keywords: introducción a MMicrosoft 365 Defender, ciberseguridad, amenazas persistentes avanzadas, seguridad empresarial, dispositivos, dispositivos, identidad, usuarios, datos, aplicaciones, incidentes, investigación automatizada y corrección, búsqueda avanzada
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 32defdf459ec65ba0fd268a5a7c84851e9014efa
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934050"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

> ¿Quiere experimentar Microsoft 365 Defender? Puede [evaluarlo en un entorno de pruebas](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o bien [ejecutar el proyecto piloto en producción](m365d-pilot.md?ocid=cx-evalpilot).
>

Microsoft 365 Defender es un conjunto de aplicaciones unificado de defensa empresarial previa y posterior a la vulneración que coordina de forma nativa la detección, prevención, investigación y respuesta entre extremos, identidades, correo electrónico y aplicaciones para proporcionar protección integrada contra ataques sofisticados.

Con la solución integrada de Microsoft 365 Defender, los profesionales de seguridad pueden unir las señales de amenaza que cada uno de estos productos recibe y determinar el alcance completo y el impacto de la amenaza; cómo entró en el entorno, lo que está afectado y cómo está afectando actualmente a la organización. Microsoft 365 Defender realiza acciones automáticas para evitar o detener el ataque y auto-sanar los buzones, puntos de conexión e identidades de usuario afectados.  


<center><h2>Servicios de Microsoft 365 Defender</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender para endpoint</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender para Office 365</b></center></a></td>
<td><center><b><a href="/azure-advanced-threat-protection/"><b>Microsoft Defender para la identidad</b></a></center></td>
<td><center><b><a href="/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Guía interactiva de Microsoft 365 Defender

En esta guía interactiva, aprenderás a proteger tu organización con Microsoft 365 Defender. Verá cómo Microsoft 365 Defender puede ayudarle a detectar riesgos de seguridad, investigar ataques a su organización y evitar actividades nocivas automáticamente.

[Eche un vistazo a la guía interactiva](https://aka.ms/M365Defender-InteractiveGuide)



El conjunto de aplicaciones de Microsoft 365 Defender protege: 
- **Endpoints with Microsoft Defender for Endpoint:** Microsoft Defender for Endpoint es una plataforma de extremo unificada para la protección preventiva, la detección posterior a la infracción, la investigación automatizada y la respuesta. 
- Correo electrónico y colaboración con **Microsoft Defender para Office 365:** Defender para Office 365 protege su organización contra las amenazas malintencionadas que suponen los mensajes de correo electrónico, los vínculos (URL) y las herramientas de colaboración. 
- Identidades con Microsoft Defender para identidad y **Azure AD Identity Protection:** Microsoft Defender para identidad usa señales de Active Directory para identificar, detectar e investigar amenazas avanzadas, identidades comprometidas y acciones malintencionadas dirigidas a su organización. 
- **Aplicaciones con seguridad de Microsoft Cloud App:** la seguridad de Microsoft Cloud App es una solución completa entre SaaS que ofrece una visibilidad profunda, controles de datos sólidos y una protección contra amenazas mejorada para las aplicaciones en la nube. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

La capa entre productos única de Microsoft 365 Defender aumenta los componentes individuales del conjunto de aplicaciones para:
- Ayudar a proteger contra ataques y coordinar respuestas defensivas en todo el conjunto de aplicaciones a través del uso compartido de señales y acciones automatizadas
- Narra la historia completa del ataque entre alertas de productos, comportamientos y contexto para los equipos de seguridad uniendo datos en alertas, eventos sospechosos y activos afectados a "incidentes"
- Automatizar la respuesta al riesgo desencadenando la recuperación automática de activos afectados a través de la corrección automatizada
- Permitir que los equipos de seguridad realicen búsquedas de amenazas detalladas y eficaces entre los datos de punto de conexión y de Office

![Imagen de la página de información general sobre incidentes](../../media/overview-incident.png) <br>
Incidente entre productos (Información general)

![Imagen de la cola de alertas](../../media/incident-list.png)<br>
Todas las alertas relacionadas en los productos del conjunto de servicios se correlacionan en un solo incidente (vista de alertas)

![Imagen de la cola de incidentes](../../media/advanced-hunting.png)<br>
Búsqueda basada en consultas en la parte superior de los datos sin procesar de correo electrónico y punto de conexión


Las características entre productos de Microsoft 365 Defender incluyen: 
- **Panel único de** vidrio entre productos: vista central de toda la información sobre detecciones, activos afectados, acciones automatizadas realizadas y pruebas relacionadas en una sola cola y un único panel en [security.microsoft.com](https://security.microsoft.com). 
- Cola de incidentes **combinados:** para ayudar a los profesionales de seguridad a centrarse en lo que es fundamental al garantizar que el ámbito de ataque completo, los activos afectados y las acciones de corrección automatizadas se agrupan y se ponen a la superficie de forma oportuna. 
- **Respuesta automática a las amenazas:** la información de amenazas críticas se comparte en tiempo real entre los productos de Microsoft 365 Defender para ayudar a detener la progresión de un ataque. Por ejemplo, si se detecta un archivo malintencionado en un extremo protegido por Microsoft Defender para endpoint, indicará a Defender para Office 365 que analice y quite el archivo de todos los mensajes de correo electrónico. Todo el conjunto de seguridad de Microsoft 365 bloqueará el archivo a la vista.
- Recuperación automática para **dispositivos, identidades** de usuario y buzones en peligro: Microsoft 365 Defender usa acciones automáticas con tecnología de IA y libros de juegos para corregir los activos afectados de nuevo a un estado seguro. Microsoft 365 Defender aprovecha las capacidades de corrección automática de los productos del conjunto de aplicaciones para garantizar que todos los activos afectados relacionados con un incidente se remedian automáticamente siempre que sea posible.
- **Búsqueda de amenazas** entre productos: los equipos de seguridad pueden aprovechar sus conocimientos organizativos únicos para buscar signos de peligro mediante la creación de sus propias consultas personalizadas sobre los datos sin procesar recopilados por los distintos productos de protección. Microsoft 365 Defender proporciona acceso basado en consultas a 30 días de señales sin procesar históricas y datos de alerta en todos los puntos de conexión y datos de Microsoft Defender para Office 365. 


## <a name="get-started"></a>Comenzar
Se deben cumplir los requisitos de licencias de Microsoft 365 Defender para poder habilitar el servicio en el Centro de seguridad de Microsoft 365 en [security.microsoft.com](https://security.microsoft.com). Para obtener más información, lea:
- [Requisitos de licencia](prerequisites.md#licensing-requirements)
- [Activar Microsoft 365 Defender](m365d-enable.md)


## <a name="see-also"></a>Ver también
- [Implementar capacidades de protección contra amenazas en Microsoft 365 E5](https://docs.microsoft.com/microsoft-365/solutions/deploy-threat-protection)
