---
title: Microsoft 365 Defender
description: Microsoft 365 Defender es una solución coordinada de protección contra amenazas diseñada para proteger dispositivos, identidades, datos y aplicaciones
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
ms.openlocfilehash: 59b963055819ee7d84a793fbedb8e87226528e35
ms.sourcegitcommit: 7883556c05ceef228dc329f715e8a6213b40d921
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2021
ms.locfileid: "58931241"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

> ¿Quiere experimentar Microsoft 365 Defender? Puede [evaluarlo en un entorno de pruebas](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o bien [ejecutar el proyecto piloto en producción](m365d-pilot.md?ocid=cx-evalpilot).
>

Microsoft 365 Defender es un conjunto de aplicaciones unificado de defensa empresarial previa y posterior a la vulneración que coordina de forma nativa la detección, prevención, investigación y respuesta entre extremos, identidades, correo electrónico y aplicaciones para proporcionar protección integrada contra ataques sofisticados.

Con la solución Microsoft 365 Defender integrada, los profesionales de seguridad pueden unir las señales de amenaza que cada uno de estos productos reciben y determinar el alcance completo y el impacto de la amenaza; cómo entró en el entorno, lo que está afectado y cómo está afectando actualmente a la organización. Microsoft 365 Defender realiza acciones automáticas para evitar o detener el ataque y auto-sanar los buzones, puntos de conexión e identidades de usuario afectados.  


<center><h2>Microsoft 365 Defender servicios</center></h2>
<table><tr><td><center><b><a href="/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint"><b>Microsoft Defender para endpoint</b></center></a></td>
<td><center><b><a href="/microsoft-365/security/office-365-security/overview"><b>Microsoft Defender para Office 365</b></center></a></td>
<td><center><b><a href="/defender-for-identity/"><b>Microsoft Defender para la identidad</b></a></center></td>
<td><center><b><a href="/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Microsoft 365 Defender guía interactiva

En esta guía interactiva, aprenderá a proteger su organización con Microsoft 365 Defender. Verá cómo los Microsoft 365 Defender pueden ayudarle a detectar riesgos de seguridad, investigar ataques a su organización y evitar actividades nocivas automáticamente.

[Eche un vistazo a la guía interactiva](https://aka.ms/M365Defender-InteractiveGuide)



El conjunto de aplicaciones de Microsoft 365 Defender protege: 
- **Endpoints with Defender for Endpoint:** Defender for Endpoint es una plataforma de extremo unificada para la protección preventiva, la detección posterior a la infracción, la investigación automatizada y la respuesta. 
- Correo electrónico y colaboración con **Defender para Office 365:** Defender para Office 365 protege su organización contra las amenazas malintencionadas que suponen los mensajes de correo electrónico, los vínculos (URL) y las herramientas de colaboración. 
- **Identities with Defender for Identity and Azure Active Directory (Azure AD) Identity Protection:** Defender for Identity usa las señales locales de Servicios de dominio de Active Directory (AD DS) para identificar, detectar e investigar amenazas avanzadas, identidades comprometidas y acciones internas malintencionadas dirigidas a su organización. Azure AD Identity Protection automatiza la detección y corrección de riesgos basados en identidades en Azure AD basado en la nube.
- **Aplicaciones con seguridad de Microsoft Cloud App:** la seguridad de Microsoft Cloud App es una solución completa entre SaaS que ofrece una visibilidad profunda, controles de datos sólidos y una protección contra amenazas mejorada para las aplicaciones en la nube. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Microsoft 365 Defender la capa entre productos única de Microsoft 365 Defender aumenta los componentes individuales del conjunto de aplicaciones para:

- Ayuda a proteger contra ataques y coordinar respuestas defensivas en todo el conjunto a través del uso compartido de señales y acciones automatizadas.
- Narra la historia completa del ataque en alertas de productos, comportamientos y contexto para los equipos de seguridad uniendo datos de alertas, eventos sospechosos y activos afectados a "incidentes".
- Automatice la respuesta al riesgo desencadenando la recuperación automática de activos afectados a través de la corrección automatizada.
- Permitir que los equipos de seguridad realicen búsquedas de amenazas detalladas y eficaces en todos los puntos de conexión y Office datos.

Este es un ejemplo de cómo el portal de Microsoft 365 Defender correlaciona todas las alertas relacionadas en el conjunto de productos en un solo incidente.

![Ejemplo de una página de información general sobre incidentes.](../../media/overview-incident.png) <br>

Este es un ejemplo de la lista de alertas relacionadas para un incidente.

![Ejemplo de la lista de alertas de un incidente](../../media/incident-list.png)<br>

Este es un ejemplo de búsqueda basada en consultas en la parte superior de los datos sin procesar de correo electrónico y punto de conexión.

![Ejemplo de búsqueda avanzada y una consulta](../../media/advanced-hunting.png)<br>

Microsoft 365 Defender características entre productos incluyen: 

- **Panel único de** vidrio entre productos: vista central para toda la información sobre detecciones, activos afectados, acciones automatizadas realizadas y pruebas relacionadas en una sola cola y un único panel en [security.microsoft.com](https://security.microsoft.com). 
- Cola de incidentes **combinados:** para ayudar a los profesionales de seguridad a centrarse en lo que es fundamental al garantizar que el ámbito de ataque completo, los activos afectados y las acciones de corrección automatizadas se agrupan y se ponen a la superficie de forma oportuna. 
- **Respuesta automática a las amenazas:** la información crítica sobre amenazas se comparte en tiempo real entre los Microsoft 365 Defender para ayudar a detener la progresión de un ataque. 

   Por ejemplo, si se detecta un archivo malintencionado en un extremo protegido por Defender for Endpoint, le indicará a Defender que Office 365 analice y quite el archivo de todos los mensajes de correo electrónico. Todo el conjunto de seguridad del conjunto de Microsoft 365 bloqueará el archivo a la vista.
- **Recuperación** automática para dispositivos, identidades de usuario y buzones en peligro: Microsoft 365 Defender usa acciones automáticas con tecnología de IA y libros de reproducción para corregir los activos afectados de nuevo a un estado seguro. Microsoft 365 Defender aprovecha las capacidades de corrección automática de los productos del conjunto de programas para garantizar que todos los activos afectados relacionados con un incidente se remedian automáticamente siempre que sea posible.
- **Búsqueda de amenazas** entre productos: los equipos de seguridad pueden aprovechar sus conocimientos organizativos únicos para buscar signos de peligro mediante la creación de sus propias consultas personalizadas sobre los datos sin procesar recopilados por los distintos productos de protección. Microsoft 365 Defender acceso basado en consultas a 30 días de señales sin procesar históricas y datos de alerta en el punto de conexión y Defender para obtener Office 365 datos. 

## <a name="get-started"></a>Introducción

Microsoft 365 Defender requisitos de licencia deben cumplirse para poder habilitar el servicio en el portal de Microsoft 365 Defender en [security.microsoft.com](https://security.microsoft.com). Para más información, vea:

- [Requisitos de licencia](prerequisites.md#licensing-requirements)
- [Activar Microsoft 365 Defender](m365d-enable.md)

## <a name="training-for-security-analysts"></a>Formación para analistas de seguridad

Con esta ruta de aprendizaje de Microsoft Learn, puede comprender Microsoft 365 Defender y cómo puede ayudar a identificar, controlar y corregir las amenazas de seguridad.

|Aprendizaje:|Detectar y responder a ataques cibernéticos con Microsoft 365 Defender|
|---|---|
|![Microsoft 365 Defender de aprendizaje.](../../media/microsoft-365-defender/m365-defender-training.png)|Microsoft 365 Defender unifica las señales de amenazas entre puntos de conexión, identidades, correo electrónico y aplicaciones para proporcionar una protección integrada frente ataques cibernéticos sofisticados. Microsoft 365 Defender es una experiencia central desde la cual investigar y responder a incidentes y buscar proactivamente actividades de ciberseguridad malintencionadas en curso.<p> 1 h 38 min - Learning path - 5 módulos|

> [!div class="nextstepaction"]
> [Iniciar >](/learn/paths/defender-detect-respond/)


## <a name="see-also"></a>Consulte también
- [Implementar capacidades de protección contra amenazas en Microsoft 365 E5](/microsoft-365/solutions/deploy-threat-protection)
